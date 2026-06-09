# CImpISequentialStream::Write(void const *,ulong,ulong *)

- ea: `0x1001d650`
- end: `0x1001d7e2`
- name: `?Write@CImpISequentialStream@@UAGJPBXKPAK@Z`
- size: `402`
- prototype: `int(CImpISequentialStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001c680`
- `0x1001c6d0`
- `0x1001d650`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001d7c6`
- `KERNEL32!LeaveCriticalSection` at `0x1001d7c6`
- `KERNEL32!EnterCriticalSection` at `0x1001d6b6`
- `KERNEL32!EnterCriticalSection` at `0x1001d6b6`
- `msjet40!__imp__JetSetColumn@28` at `0x1001d750`
- `msjet40!__imp__JetSetColumn@28` at `0x1001d750`

## pseudocode

```c
int __stdcall CImpISequentialStream::Write(
        CImpISequentialStream *this,
        void *pvData,
        unsigned int cbData,
        unsigned int *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  int v5; // ebx
  _DWORD *v6; // eax
  CTransactionState *v7; // ecx
  int isZombie; // eax
  JET_ERR v9; // eax
  unsigned int v10; // eax
  CExtBuffer *v12; // [esp+0h] [ebp-20h]
  unsigned int v13; // [esp+4h] [ebp-1Ch]

  v4 = 0;
  if ( a4 )
    *a4 = 0;
  if ( *((_DWORD *)this + 2) == 1 )
  {
    v5 = -2147418113;
    goto LABEL_27;
  }
  v4 = (struct _RTL_CRITICAL_SECTION *)(*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 4) + 16))(*((_DWORD *)this + 4));
  EnterCriticalSection(v4);
  if ( (*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 4) + 20))(*((_DWORD *)this + 4)) )
  {
    v6 = (_DWORD *)(*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 4) + 20))(*((_DWORD *)this + 4));
    if ( v6[4] == 1 && (v7 = (CTransactionState *)v6[2]) != 0 )
      isZombie = CTransactionState::isZombie(v7);
    else
      isZombie = v6[3];
    if ( isZombie == 1 )
    {
      v5 = -2147418113;
      goto LABEL_27;
    }
  }
  if ( !pvData && !cbData )
  {
    v5 = -2147287031;
    goto LABEL_27;
  }
  if ( *((_DWORD *)this + 11) == 1 )
  {
    v5 = -2147287035;
    goto LABEL_27;
  }
  v9 = JetSetColumn(
         *((_DWORD *)this + 5),
         *((_DWORD *)this + 6),
         *((_DWORD *)this + 7),
         pvData,
         cbData,
         *((_DWORD *)this + 8) != 1,
         0);
  if ( v9 <= -1108 )
  {
    switch ( v9 )
    {
      case -1108:
        v5 = -2147286782;
        goto LABEL_27;
      case -1609:
        v5 = -2147286781;
        goto LABEL_27;
      case -1503:
        v5 = -2147286928;
        goto LABEL_27;
    }
    goto LABEL_25;
  }
  if ( v9 )
  {
LABEL_25:
    v5 = -2147467259;
    goto LABEL_27;
  }
  *((_DWORD *)this + 8) = 0;
  v5 = 0;
  *((_DWORD *)CExtBuffer::GetPtrOfExtBuffer(v12, v13) + 1) = 2;
LABEL_27:
  if ( a4 )
  {
    v10 = cbData;
    if ( v5 < 0 )
      v10 = 0;
    *a4 = v10;
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return v5;
}

```

## disassembly

```asm
0x1001d650  mov     edi, edi
0x1001d652  push    ebp
0x1001d653  mov     ebp, esp
0x1001d655  push    0FFFFFFFFh
0x1001d657  push    offset ?Unadvise@CRowsetConnectionPoint@@UAGJK@Z_SEH
0x1001d65c  mov     eax, large fs:0
0x1001d662  push    eax
0x1001d663  push    ecx
0x1001d664  push    ebx
0x1001d665  push    esi
0x1001d666  push    edi; unsigned int
0x1001d667  mov     eax, ___security_cookie
0x1001d66c  xor     eax, ebp
0x1001d66e  push    eax; this
0x1001d66f  lea     eax, [ebp+var_C]
0x1001d672  mov     large fs:0, eax
0x1001d678  xor     esi, esi
0x1001d67a  mov     [ebp+var_10], esi
0x1001d67d  mov     ebx, [ebp+arg_C]
0x1001d680  mov     [ebp+var_4], esi
0x1001d683  test    ebx, ebx
0x1001d685  jz      short loc_1001D689
0x1001d687  mov     [ebx], esi
0x1001d689  mov     ebx, [ebp+this]
0x1001d68c  cmp     dword ptr [ebx+8], 1
0x1001d690  jnz     short loc_1001D69C
0x1001d692  mov     ebx, 8000FFFFh
0x1001d697  jmp     loc_1001D7AE
0x1001d69c  mov     edi, [ebx+10h]
0x1001d69f  mov     eax, [edi]
0x1001d6a1  mov     esi, [eax+10h]
0x1001d6a4  mov     ecx, esi
0x1001d6a6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001d6ac  mov     ecx, edi
0x1001d6ae  call    esi
0x1001d6b0  mov     esi, eax
0x1001d6b2  push    esi; lpCriticalSection
0x1001d6b3  mov     [ebp+var_10], esi
0x1001d6b6  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001d6bc  mov     ebx, [ebx+10h]
0x1001d6bf  mov     eax, [ebx]
0x1001d6c1  mov     edi, [eax+14h]
0x1001d6c4  mov     ecx, edi
0x1001d6c6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001d6cc  mov     ecx, ebx
0x1001d6ce  call    edi
0x1001d6d0  test    eax, eax
0x1001d6d2  jz      short loc_1001D711
0x1001d6d4  mov     ebx, [ebp+this]
0x1001d6d7  mov     ebx, [ebx+10h]
0x1001d6da  mov     eax, [ebx]
0x1001d6dc  mov     edi, [eax+14h]
0x1001d6df  mov     ecx, edi
0x1001d6e1  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001d6e7  mov     ecx, ebx
0x1001d6e9  call    edi
0x1001d6eb  cmp     dword ptr [eax+10h], 1
0x1001d6ef  jnz     short loc_1001D6FF
0x1001d6f1  mov     ecx, [eax+8]; this
0x1001d6f4  test    ecx, ecx
0x1001d6f6  jz      short loc_1001D6FF
0x1001d6f8  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1001d6fd  jmp     short loc_1001D702
0x1001d6ff  mov     eax, [eax+0Ch]
0x1001d702  cmp     eax, 1
0x1001d705  jnz     short loc_1001D711
0x1001d707  mov     ebx, 8000FFFFh
0x1001d70c  jmp     loc_1001D7AE
0x1001d711  mov     edx, [ebp+pvData]
0x1001d714  mov     ecx, [ebp+cbData]
0x1001d717  test    edx, edx
0x1001d719  jnz     short loc_1001D729
0x1001d71b  test    ecx, ecx
0x1001d71d  jnz     short loc_1001D729
0x1001d71f  mov     ebx, 80030009h
0x1001d724  jmp     loc_1001D7AE
0x1001d729  mov     ebx, [ebp+this]
0x1001d72c  cmp     dword ptr [ebx+2Ch], 1
0x1001d730  jnz     short loc_1001D739
0x1001d732  mov     ebx, 80030005h
0x1001d737  jmp     short loc_1001D7AE
0x1001d739  xor     eax, eax
0x1001d73b  cmp     dword ptr [ebx+20h], 1
0x1001d73f  push    0; psetinfo
0x1001d741  setnz   al
0x1001d744  push    eax; grbit
0x1001d745  push    ecx; cbData
0x1001d746  push    edx; pvData
0x1001d747  push    dword ptr [ebx+1Ch]; columnid
0x1001d74a  push    dword ptr [ebx+18h]; tableid
0x1001d74d  push    dword ptr [ebx+14h]; sesid
0x1001d750  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1001d756  cmp     eax, 0FFFFFBACh
0x1001d75b  jg      short loc_1001D782
0x1001d75d  jz      short loc_1001D77B
0x1001d75f  cmp     eax, 0FFFFF9B7h
0x1001d764  jz      short loc_1001D774
0x1001d766  cmp     eax, 0FFFFFA21h
0x1001d76b  jnz     short loc_1001D786
0x1001d76d  mov     ebx, 80030070h
0x1001d772  jmp     short loc_1001D7AE
0x1001d774  mov     ebx, 80030103h
0x1001d779  jmp     short loc_1001D7AE
0x1001d77b  mov     ebx, 80030102h
0x1001d780  jmp     short loc_1001D7AE
0x1001d782  test    eax, eax
0x1001d784  jz      short loc_1001D78D
0x1001d786  mov     ebx, 80004005h
0x1001d78b  jmp     short loc_1001D7AE
0x1001d78d  mov     ecx, [ebx+10h]
0x1001d790  mov     dword ptr [ebx+20h], 0
0x1001d797  mov     edx, [ecx+0E0h]
0x1001d79d  mov     ecx, [ecx+68h]
0x1001d7a0  call    ?GetPtrOfExtBuffer@CExtBuffer@@QAGPAXK@Z; CExtBuffer::GetPtrOfExtBuffer(ulong)
0x1001d7a5  xor     ebx, ebx
0x1001d7a7  mov     dword ptr [eax+4], 2
0x1001d7ae  mov     ecx, [ebp+arg_C]
0x1001d7b1  test    ecx, ecx
0x1001d7b3  jz      short loc_1001D7C1
0x1001d7b5  mov     eax, [ebp+cbData]
0x1001d7b8  xor     edx, edx
0x1001d7ba  test    ebx, ebx
0x1001d7bc  cmovs   eax, edx
0x1001d7bf  mov     [ecx], eax
0x1001d7c1  test    esi, esi
0x1001d7c3  jz      short loc_1001D7CC
0x1001d7c5  push    esi; lpCriticalSection
0x1001d7c6  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001d7cc  mov     eax, ebx
0x1001d7ce  mov     ecx, [ebp+var_C]
0x1001d7d1  mov     large fs:0, ecx
0x1001d7d8  pop     ecx
0x1001d7d9  pop     edi
0x1001d7da  pop     esi
0x1001d7db  pop     ebx
0x1001d7dc  mov     esp, ebp
0x1001d7de  pop     ebp
0x1001d7df  retn    10h
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
