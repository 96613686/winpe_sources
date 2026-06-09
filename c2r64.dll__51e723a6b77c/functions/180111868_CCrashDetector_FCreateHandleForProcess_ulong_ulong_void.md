# CCrashDetector::FCreateHandleForProcess(ulong,ulong *,void * *)

- ea: `0x180111868`
- end: `0x180111a32`
- name: `?FCreateHandleForProcess@CCrashDetector@@QEAA_NKPEAKPEAPEAX@Z`
- size: `458`
- prototype: `bool __fastcall(CCrashDetector *__hidden this, unsigned int, unsigned int *, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180111d98`
- `0x180112824`
- `0x180113a24`

## callees

- `0x1800264b4`
- `0x18002c8a8`
- `0x180037cf4`
- `0x18003e690`
- `0x180111638`
- `0x180111868`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801118fc`
- `KERNEL32!GetLastError` at `0x1801118fc`
- `KERNEL32!CloseHandle` at `0x1801118d6`
- `KERNEL32!CloseHandle` at `0x1801118f3`
- `KERNEL32!CloseHandle` at `0x1801119b6`
- `KERNEL32!CloseHandle` at `0x1801119d0`
- `KERNEL32!CloseHandle` at `0x180111a05`
- `KERNEL32!CloseHandle` at `0x1801118d6`
- `KERNEL32!CloseHandle` at `0x1801118f3`
- `KERNEL32!CloseHandle` at `0x1801119b6`
- `KERNEL32!CloseHandle` at `0x1801119d0`
- `KERNEL32!CloseHandle` at `0x180111a05`
- `KERNEL32!OpenProcess` at `0x1801118c5`
- `KERNEL32!OpenProcess` at `0x1801118c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall CCrashDetector::FCreateHandleForProcess(
        CCrashDetector *this,
        unsigned int a2,
        unsigned int *a3,
        void **a4)
{
  __int64 v7; // rbp
  __int64 v8; // r14
  void *v9; // rbx
  DWORD v10; // edi
  HANDLE v11; // rsi
  DWORD LastError; // eax
  __int64 v13; // rdx
  BOOL v14; // eax
  HANDLE v15; // rbp
  char v16; // r14
  int v17; // edi
  __int64 v18; // rcx
  struct _SECURITY_ATTRIBUTES *v20; // [rsp+28h] [rbp-480h]
  int v21; // [rsp+40h] [rbp-468h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-464h]
  HANDLE hObject; // [rsp+48h] [rbp-460h] BYREF
  char v24[1024]; // [rsp+50h] [rbp-458h] BYREF

  v22 = a2;
  v7 = a2;
  v8 = *((_QWORD *)this + 3);
  v9 = 0;
  while ( 1 )
  {
    *a4 = 0;
    v10 = *(_DWORD *)(v8 + 4 * v7 + 28);
    *a3 = v10;
    if ( !v10 )
    {
      if ( v9 )
        CloseHandle(v9);
      return 1;
    }
    v11 = OpenProcess(0x101000u, 0, v10);
    if ( v9 )
      CloseHandle(v9);
    v9 = v11;
    if ( v10 == *(_DWORD *)(v8 + 4 * v7 + 28) )
      break;
    if ( v11 )
    {
      v9 = 0;
      CloseHandle(v11);
    }
  }
  LastError = GetLastError();
  if ( v11 || LastError != 87 )
  {
    v21 = 0;
    hObject = 0;
    LODWORD(v20) = *((_DWORD *)this + 15);
    sub_180111638(v24, v13, *(_QWORD *)(*((_QWORD *)this + 6) + 1080LL), v22, v10);
    v14 = MsoFOpenCreateEvent(&hObject, v24, 1, 0, &v21, v20, *((_DWORD *)&vdwSecurityModes + *((int *)this + 15)));
    v15 = hObject;
    if ( v14 && hObject )
    {
      v16 = 1;
      v17 = v21;
      if ( !v21 )
        v17 = MsoWaitForSingleObject(hObject, 0) == 258;
    }
    else
    {
      v16 = 0;
      v17 = v21;
    }
    if ( v15 )
      CloseHandle(v15);
    if ( !v16 || v17 )
    {
      if ( v11 )
      {
        v9 = 0;
        CloseHandle(v11);
      }
    }
    *a4 = v9;
    if ( !v16 )
    {
      v18 = 507556240;
LABEL_23:
      MsoShipAssertTagProc(v18);
      return 0;
    }
    if ( !v17 && !v9 )
    {
      v18 = 507556239;
      goto LABEL_23;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180111868  push    rbx
0x18011186a  push    rbp
0x18011186b  push    rsi
0x18011186c  push    rdi
0x18011186d  push    r12
0x18011186f  push    r13
0x180111871  push    r14
0x180111873  push    r15
0x180111875  sub     rsp, 468h
0x18011187c  mov     rax, cs:__security_cookie
0x180111883  xor     rax, rsp
0x180111886  mov     [rsp+4A8h+var_58], rax
0x18011188e  mov     r15, r9
0x180111891  mov     r12, r8
0x180111894  mov     [rsp+4A8h+var_464], edx
0x180111898  mov     r13, rcx
0x18011189b  mov     ebp, edx
0x18011189d  mov     r14, [rcx+18h]
0x1801118a1  xor     ebx, ebx
0x1801118a3  mov     qword ptr [r15], 0
0x1801118aa  mov     edi, [r14+rbp*4+1Ch]
0x1801118af  mov     [r12], edi
0x1801118b3  test    edi, edi
0x1801118b5  jz      loc_1801119FD
0x1801118bb  mov     r8d, edi; dwProcessId
0x1801118be  xor     edx, edx; bInheritHandle
0x1801118c0  mov     ecx, 101000h; dwDesiredAccess
0x1801118c5  call    cs:__imp_OpenProcess
0x1801118cb  mov     rsi, rax
0x1801118ce  test    rbx, rbx
0x1801118d1  jz      short loc_1801118DD
0x1801118d3  mov     rcx, rbx; hObject
0x1801118d6  call    cs:__imp_CloseHandle
0x1801118dc  nop
0x1801118dd  mov     rbx, rsi
0x1801118e0  mov     eax, [r14+rbp*4+1Ch]
0x1801118e5  cmp     edi, eax
0x1801118e7  jz      short loc_1801118FC
0x1801118e9  test    rsi, rsi
0x1801118ec  jz      short loc_1801118A3
0x1801118ee  xor     ebx, ebx
0x1801118f0  mov     rcx, rsi; hObject
0x1801118f3  call    cs:__imp_CloseHandle
0x1801118f9  nop
0x1801118fa  jmp     short loc_1801118A3
0x1801118fc  call    cs:__imp_GetLastError
0x180111902  test    rsi, rsi
0x180111905  jnz     short loc_180111910
0x180111907  cmp     eax, 57h ; 'W'
0x18011190a  jz      loc_180111A0C
0x180111910  mov     [rsp+4A8h+var_468], 0
0x180111918  mov     [rsp+4A8h+hObject], 0
0x180111921  mov     ecx, [r13+3Ch]
0x180111925  mov     rax, [r13+30h]
0x180111929  mov     dword ptr [rsp+4A8h+var_480], ecx; struct _SECURITY_ATTRIBUTES *
0x18011192d  mov     dword ptr [rsp+4A8h+var_488], edi
0x180111931  mov     r9d, [rsp+4A8h+var_464]
0x180111936  mov     r8, [rax+438h]
0x18011193d  lea     rcx, [rsp+4A8h+var_458]
0x180111942  call    sub_180111638
0x180111947  movsxd  rax, dword ptr [r13+3Ch]
0x18011194b  lea     rcx, ?vdwSecurityModes@@3QBKB; ulong const near * const vdwSecurityModes
0x180111952  mov     eax, [rcx+rax*4]
0x180111955  mov     [rsp+4A8h+var_478], eax; unsigned int
0x180111959  lea     rax, [rsp+4A8h+var_468]
0x18011195e  mov     [rsp+4A8h+var_488], rax; int *
0x180111963  xor     r9d, r9d; int
0x180111966  lea     r8d, [r9+1]; int
0x18011196a  lea     rdx, [rsp+4A8h+var_458]; char *
0x18011196f  lea     rcx, [rsp+4A8h+hObject]; void **
0x180111974  call    ?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z; MsoFOpenCreateEvent(void * *,char const *,int,int,int *,_SECURITY_ATTRIBUTES *,ulong)
0x180111979  mov     rbp, [rsp+4A8h+hObject]
0x18011197e  test    eax, eax
0x180111980  jz      short loc_1801119A7
0x180111982  test    rbp, rbp
0x180111985  jz      short loc_1801119A7
0x180111987  mov     r14b, 1
0x18011198a  mov     edi, [rsp+4A8h+var_468]
0x18011198e  test    edi, edi
0x180111990  jnz     short loc_1801119AE
0x180111992  xor     edx, edx; dwMilliseconds
0x180111994  mov     rcx, rbp; hHandle
0x180111997  call    MsoWaitForSingleObject
0x18011199c  cmp     eax, 102h
0x1801119a1  setz    dil
0x1801119a5  jmp     short loc_1801119AE
0x1801119a7  xor     r14b, r14b
0x1801119aa  mov     edi, [rsp+4A8h+var_468]
0x1801119ae  test    rbp, rbp
0x1801119b1  jz      short loc_1801119BD
0x1801119b3  mov     rcx, rbp; hObject
0x1801119b6  call    cs:__imp_CloseHandle
0x1801119bc  nop
0x1801119bd  test    r14b, r14b
0x1801119c0  jz      short loc_1801119C6
0x1801119c2  test    edi, edi
0x1801119c4  jz      short loc_1801119D7
0x1801119c6  test    rsi, rsi
0x1801119c9  jz      short loc_1801119D7
0x1801119cb  xor     ebx, ebx
0x1801119cd  mov     rcx, rsi; hObject
0x1801119d0  call    cs:__imp_CloseHandle
0x1801119d6  nop
0x1801119d7  mov     [r15], rbx
0x1801119da  test    r14b, r14b
0x1801119dd  jnz     short loc_1801119ED
0x1801119df  mov     ecx, 1E40B190h
0x1801119e4  call    MsoShipAssertTagProc
0x1801119e9  xor     al, al
0x1801119eb  jmp     short loc_180111A0E
0x1801119ed  test    edi, edi
0x1801119ef  jnz     short loc_180111A0C
0x1801119f1  test    rbx, rbx
0x1801119f4  jnz     short loc_180111A0C
0x1801119f6  mov     ecx, 1E40B18Fh
0x1801119fb  jmp     short loc_1801119E4
0x1801119fd  test    rbx, rbx
0x180111a00  jz      short loc_180111A0C
0x180111a02  mov     rcx, rbx; hObject
0x180111a05  call    cs:__imp_CloseHandle
0x180111a0b  nop
0x180111a0c  mov     al, 1
0x180111a0e  mov     rcx, [rsp+4A8h+var_58]
0x180111a16  xor     rcx, rsp; StackCookie
0x180111a19  call    __security_check_cookie
0x180111a1e  add     rsp, 468h
0x180111a25  pop     r15
0x180111a27  pop     r14
0x180111a29  pop     r13
0x180111a2b  pop     r12
0x180111a2d  pop     rdi
0x180111a2e  pop     rsi
0x180111a2f  pop     rbp
0x180111a30  pop     rbx
0x180111a31  retn
```
