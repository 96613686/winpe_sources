# LongBinaryILockBytes::ReadAt(_ULARGE_INTEGER,void *,ulong,ulong *)

- ea: `0x1001caa0`
- end: `0x1001cbd0`
- name: `?ReadAt@LongBinaryILockBytes@@UAGJT_ULARGE_INTEGER@@PAXKPAK@Z`
- size: `304`
- prototype: `int __stdcall(LongBinaryILockBytes *__hidden this, union _ULARGE_INTEGER, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001c6d0`
- `0x1001caa0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001cbb4`
- `KERNEL32!LeaveCriticalSection` at `0x1001cbb4`
- `KERNEL32!EnterCriticalSection` at `0x1001cb1f`
- `KERNEL32!EnterCriticalSection` at `0x1001cb1f`

## pseudocode

```c
int __stdcall LongBinaryILockBytes::ReadAt(
        LongBinaryILockBytes *this,
        union _ULARGE_INTEGER a2,
        void *a3,
        unsigned int a4,
        unsigned int *a5)
{
  struct _RTL_CRITICAL_SECTION *v6; // esi
  _DWORD *v7; // eax
  CTransactionState *v8; // ecx
  int isZombie; // eax
  int v10; // edi

  if ( a5 )
    *a5 = 0;
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
  else if ( !a4 || a3 )
  {
    v10 = (*(int (__thiscall **)(_DWORD, _DWORD, DWORD, DWORD, void *, unsigned int, unsigned int *))(**((_DWORD **)this + 5) + 12))(
            *(_DWORD *)(**((_DWORD **)this + 5) + 12),
            *((_DWORD *)this + 5),
            a2.LowPart,
            a2.HighPart,
            a3,
            a4,
            a5);
  }
  else
  {
    v10 = -2147287031;
  }
  if ( v6 )
    LeaveCriticalSection(v6);
  return v10;
}

```

## disassembly

```asm
0x1001caa0  mov     edi, edi
0x1001caa2  push    ebp
0x1001caa3  mov     ebp, esp
0x1001caa5  push    0FFFFFFFFh
0x1001caa7  push    offset ?Unadvise@CRowsetConnectionPoint@@UAGJK@Z_SEH
0x1001caac  mov     eax, large fs:0
0x1001cab2  push    eax
0x1001cab3  push    ecx
0x1001cab4  push    ebx
0x1001cab5  push    esi
0x1001cab6  push    edi
0x1001cab7  mov     eax, ___security_cookie
0x1001cabc  xor     eax, ebp
0x1001cabe  push    eax
0x1001cabf  lea     eax, [ebp+var_C]
0x1001cac2  mov     large fs:0, eax
0x1001cac8  mov     [ebp+var_10], 0
0x1001cacf  mov     eax, [ebp+arg_14]
0x1001cad2  mov     [ebp+var_4], 0
0x1001cad9  test    eax, eax
0x1001cadb  jz      short loc_1001CAE3
0x1001cadd  mov     dword ptr [eax], 0
0x1001cae3  mov     ebx, [ebp+this]
0x1001cae6  cmp     dword ptr [ebx+8], 1
0x1001caea  jnz     short loc_1001CB05
0x1001caec  mov     eax, 8000FFFFh
0x1001caf1  mov     ecx, [ebp+var_C]
0x1001caf4  mov     large fs:0, ecx
0x1001cafb  pop     ecx
0x1001cafc  pop     edi
0x1001cafd  pop     esi
0x1001cafe  pop     ebx
0x1001caff  mov     esp, ebp
0x1001cb01  pop     ebp
0x1001cb02  retn    18h
0x1001cb05  mov     edi, [ebx+10h]
0x1001cb08  mov     eax, [edi]
0x1001cb0a  mov     esi, [eax+10h]
0x1001cb0d  mov     ecx, esi
0x1001cb0f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001cb15  mov     ecx, edi
0x1001cb17  call    esi
0x1001cb19  mov     esi, eax
0x1001cb1b  push    esi; lpCriticalSection
0x1001cb1c  mov     [ebp+var_10], esi
0x1001cb1f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001cb25  mov     ebx, [ebx+10h]
0x1001cb28  mov     eax, [ebx]
0x1001cb2a  mov     edi, [eax+14h]
0x1001cb2d  mov     ecx, edi
0x1001cb2f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001cb35  mov     ecx, ebx
0x1001cb37  call    edi
0x1001cb39  test    eax, eax
0x1001cb3b  jz      short loc_1001CB77
0x1001cb3d  mov     ebx, [ebp+this]
0x1001cb40  mov     ebx, [ebx+10h]
0x1001cb43  mov     eax, [ebx]
0x1001cb45  mov     edi, [eax+14h]
0x1001cb48  mov     ecx, edi
0x1001cb4a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001cb50  mov     ecx, ebx
0x1001cb52  call    edi
0x1001cb54  cmp     dword ptr [eax+10h], 1
0x1001cb58  jnz     short loc_1001CB68
0x1001cb5a  mov     ecx, [eax+8]; this
0x1001cb5d  test    ecx, ecx
0x1001cb5f  jz      short loc_1001CB68
0x1001cb61  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1001cb66  jmp     short loc_1001CB6B
0x1001cb68  mov     eax, [eax+0Ch]
0x1001cb6b  cmp     eax, 1
0x1001cb6e  jnz     short loc_1001CB77
0x1001cb70  mov     edi, 8000FFFFh
0x1001cb75  jmp     short loc_1001CBAF
0x1001cb77  mov     ebx, [ebp+arg_10]
0x1001cb7a  mov     edx, [ebp+arg_C]
0x1001cb7d  test    ebx, ebx
0x1001cb7f  jz      short loc_1001CB8C
0x1001cb81  test    edx, edx
0x1001cb83  jnz     short loc_1001CB8C
0x1001cb85  mov     edi, 80030009h
0x1001cb8a  jmp     short loc_1001CBAF
0x1001cb8c  push    [ebp+arg_14]
0x1001cb8f  mov     eax, [ebp+this]
0x1001cb92  push    ebx
0x1001cb93  push    edx
0x1001cb94  push    dword ptr [ebp+arg_4+4]
0x1001cb97  mov     ecx, [eax+14h]
0x1001cb9a  push    dword ptr [ebp+arg_4]
0x1001cb9d  push    ecx
0x1001cb9e  mov     eax, [ecx]
0x1001cba0  mov     edi, [eax+0Ch]
0x1001cba3  mov     ecx, edi
0x1001cba5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001cbab  call    edi
0x1001cbad  mov     edi, eax
0x1001cbaf  test    esi, esi
0x1001cbb1  jz      short loc_1001CBBA
0x1001cbb3  push    esi; lpCriticalSection
0x1001cbb4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001cbba  mov     eax, edi
0x1001cbbc  mov     ecx, [ebp+var_C]
0x1001cbbf  mov     large fs:0, ecx
0x1001cbc6  pop     ecx
0x1001cbc7  pop     edi
0x1001cbc8  pop     esi
0x1001cbc9  pop     ebx
0x1001cbca  mov     esp, ebp
0x1001cbcc  pop     ebp
0x1001cbcd  retn    18h
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
