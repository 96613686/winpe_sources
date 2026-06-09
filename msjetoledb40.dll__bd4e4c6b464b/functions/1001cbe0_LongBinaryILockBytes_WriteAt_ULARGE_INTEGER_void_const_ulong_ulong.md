# LongBinaryILockBytes::WriteAt(_ULARGE_INTEGER,void const *,ulong,ulong *)

- ea: `0x1001cbe0`
- end: `0x1001cd0e`
- name: `?WriteAt@LongBinaryILockBytes@@UAGJT_ULARGE_INTEGER@@PBXKPAK@Z`
- size: `302`
- prototype: `int(LongBinaryILockBytes *__hidden this, union _ULARGE_INTEGER, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001c680`
- `0x1001c6d0`
- `0x1001cbe0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001ccf2`
- `KERNEL32!LeaveCriticalSection` at `0x1001ccf2`
- `KERNEL32!EnterCriticalSection` at `0x1001cc52`
- `KERNEL32!EnterCriticalSection` at `0x1001cc52`

## pseudocode

```c
int __stdcall LongBinaryILockBytes::WriteAt(
        LongBinaryILockBytes *this,
        union _ULARGE_INTEGER a2,
        const void *a3,
        unsigned int a4,
        unsigned int *a5)
{
  struct _RTL_CRITICAL_SECTION *v6; // esi
  _DWORD *v7; // eax
  CTransactionState *v8; // ecx
  int isZombie; // eax
  int v10; // edi
  int (__thiscall *v11)(_DWORD, _DWORD, DWORD, DWORD, const void *, unsigned int, unsigned int *); // ecx
  CExtBuffer *v12; // [esp+0h] [ebp-20h]
  unsigned int v13; // [esp+4h] [ebp-1Ch]

  if ( *((_DWORD *)this + 2) == 1 )
    return -2147418113;
  v6 = (struct _RTL_CRITICAL_SECTION *)(*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 4) + 16))(*((_DWORD *)this + 4));
  EnterCriticalSection(v6);
  if ( (*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 4) + 20))(*((_DWORD *)this + 4))
    && ((v7 = (_DWORD *)(*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 4) + 20))(*((_DWORD *)this + 4)), v7[4] != 1)
     || (v8 = (CTransactionState *)v7[2]) == 0
      ? (isZombie = v7[3])
      : (isZombie = CTransactionState::isZombie(v8)),
        isZombie == 1) )
  {
    v10 = -2147418113;
  }
  else
  {
    v11 = *(int (__thiscall **)(_DWORD, _DWORD, DWORD, DWORD, const void *, unsigned int, unsigned int *))(**((_DWORD **)this + 5) + 16);
    v10 = v11(v11, *((_DWORD *)this + 5), a2.LowPart, a2.HighPart, a3, a4, a5);
    if ( v10 >= 0 )
      *((_DWORD *)CExtBuffer::GetPtrOfExtBuffer(v12, v13) + 1) = 2;
  }
  if ( v6 )
    LeaveCriticalSection(v6);
  return v10;
}

```

## disassembly

```asm
0x1001cbe0  mov     edi, edi
0x1001cbe2  push    ebp
0x1001cbe3  mov     ebp, esp
0x1001cbe5  push    0FFFFFFFFh
0x1001cbe7  push    offset ?Unadvise@CRowsetConnectionPoint@@UAGJK@Z_SEH
0x1001cbec  mov     eax, large fs:0
0x1001cbf2  push    eax
0x1001cbf3  push    ecx
0x1001cbf4  push    ebx
0x1001cbf5  push    esi
0x1001cbf6  push    edi; unsigned int
0x1001cbf7  mov     eax, ___security_cookie
0x1001cbfc  xor     eax, ebp
0x1001cbfe  push    eax; this
0x1001cbff  lea     eax, [ebp+var_C]
0x1001cc02  mov     large fs:0, eax
0x1001cc08  mov     [ebp+var_10], 0
0x1001cc0f  mov     ebx, [ebp+this]
0x1001cc12  mov     [ebp+var_4], 0
0x1001cc19  cmp     dword ptr [ebx+8], 1
0x1001cc1d  jnz     short loc_1001CC38
0x1001cc1f  mov     eax, 8000FFFFh
0x1001cc24  mov     ecx, [ebp+var_C]
0x1001cc27  mov     large fs:0, ecx
0x1001cc2e  pop     ecx
0x1001cc2f  pop     edi
0x1001cc30  pop     esi
0x1001cc31  pop     ebx
0x1001cc32  mov     esp, ebp
0x1001cc34  pop     ebp
0x1001cc35  retn    18h
0x1001cc38  mov     edi, [ebx+10h]
0x1001cc3b  mov     eax, [edi]
0x1001cc3d  mov     esi, [eax+10h]
0x1001cc40  mov     ecx, esi
0x1001cc42  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001cc48  mov     ecx, edi
0x1001cc4a  call    esi
0x1001cc4c  mov     esi, eax
0x1001cc4e  push    esi; lpCriticalSection
0x1001cc4f  mov     [ebp+var_10], esi
0x1001cc52  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001cc58  mov     ebx, [ebx+10h]
0x1001cc5b  mov     eax, [ebx]
0x1001cc5d  mov     edi, [eax+14h]
0x1001cc60  mov     ecx, edi
0x1001cc62  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001cc68  mov     ecx, ebx
0x1001cc6a  call    edi
0x1001cc6c  test    eax, eax
0x1001cc6e  jz      short loc_1001CCAA
0x1001cc70  mov     ebx, [ebp+this]
0x1001cc73  mov     ebx, [ebx+10h]
0x1001cc76  mov     eax, [ebx]
0x1001cc78  mov     edi, [eax+14h]
0x1001cc7b  mov     ecx, edi
0x1001cc7d  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001cc83  mov     ecx, ebx
0x1001cc85  call    edi
0x1001cc87  cmp     dword ptr [eax+10h], 1
0x1001cc8b  jnz     short loc_1001CC9B
0x1001cc8d  mov     ecx, [eax+8]; this
0x1001cc90  test    ecx, ecx
0x1001cc92  jz      short loc_1001CC9B
0x1001cc94  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1001cc99  jmp     short loc_1001CC9E
0x1001cc9b  mov     eax, [eax+0Ch]
0x1001cc9e  cmp     eax, 1
0x1001cca1  jnz     short loc_1001CCAA
0x1001cca3  mov     edi, 8000FFFFh
0x1001cca8  jmp     short loc_1001CCED
0x1001ccaa  push    [ebp+arg_14]
0x1001ccad  mov     ebx, [ebp+this]
0x1001ccb0  push    [ebp+arg_10]
0x1001ccb3  push    [ebp+arg_C]
0x1001ccb6  mov     ecx, [ebx+14h]
0x1001ccb9  push    dword ptr [ebp+arg_4+4]
0x1001ccbc  push    dword ptr [ebp+arg_4]
0x1001ccbf  mov     eax, [ecx]
0x1001ccc1  push    ecx
0x1001ccc2  mov     edi, [eax+10h]
0x1001ccc5  mov     ecx, edi
0x1001ccc7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001cccd  call    edi
0x1001cccf  mov     edi, eax
0x1001ccd1  test    edi, edi
0x1001ccd3  js      short loc_1001CCED
0x1001ccd5  mov     ecx, [ebx+10h]
0x1001ccd8  mov     edx, [ecx+0E0h]
0x1001ccde  mov     ecx, [ecx+68h]
0x1001cce1  call    ?GetPtrOfExtBuffer@CExtBuffer@@QAGPAXK@Z; CExtBuffer::GetPtrOfExtBuffer(ulong)
0x1001cce6  mov     dword ptr [eax+4], 2
0x1001cced  test    esi, esi
0x1001ccef  jz      short loc_1001CCF8
0x1001ccf1  push    esi; lpCriticalSection
0x1001ccf2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001ccf8  mov     eax, edi
0x1001ccfa  mov     ecx, [ebp+var_C]
0x1001ccfd  mov     large fs:0, ecx
0x1001cd04  pop     ecx
0x1001cd05  pop     edi
0x1001cd06  pop     esi
0x1001cd07  pop     ebx
0x1001cd08  mov     esp, ebp
0x1001cd0a  pop     ebp
0x1001cd0b  retn    18h
0x1004dea0  lea     ecx, [ebp+var_10]; this
0x1004dea3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dead  nop
0x1004deae  nop
0x1004deaf  mov     edx, [esp-4+arg_4]
0x1004deb3  lea     eax, [edx+0Ch]
0x1004deb6  mov     ecx, [edx-14h]
0x1004deb9  xor     ecx, eax; StackCookie
0x1004debb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dec0  mov     eax, offset stru_1004F464
0x1004dec5  jmp     ___CxxFrameHandler3
```
