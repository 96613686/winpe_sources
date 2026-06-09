# EnumNlmLocks(void *,ulong (*)(void *,ushort *,_NLM_LOCKED_FILE *))

- ea: `0x1800223f8`
- end: `0x1800226a2`
- name: `?EnumNlmLocks@@YAKPEAXP6AK0PEAGPEAU_NLM_LOCKED_FILE@@@Z@Z`
- size: `682`
- prototype: `unsigned int __fastcall(void *, unsigned int (*)(void *, unsigned __int16 *, struct _NLM_LOCKED_FILE *))`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180018b64`

## callees

- `0x180001da6`
- `0x1800187b8`
- `0x180021600`
- `0x1800223f8`
- `0x180022754`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180022620`
- `KERNEL32!HeapFree` at `0x18002265e`
- `KERNEL32!HeapFree` at `0x180022677`
- `KERNEL32!HeapFree` at `0x180022620`
- `KERNEL32!HeapFree` at `0x18002265e`
- `KERNEL32!HeapFree` at `0x180022677`
- `KERNEL32!GetLastError` at `0x180022594`
- `KERNEL32!GetLastError` at `0x180022643`
- `KERNEL32!GetLastError` at `0x180022594`
- `KERNEL32!GetLastError` at `0x180022643`
- `KERNEL32!CloseHandle` at `0x18002263b`
- `KERNEL32!CloseHandle` at `0x18002263b`
- `KERNEL32!HeapAlloc` at `0x1800224c1`
- `KERNEL32!HeapAlloc` at `0x1800224c1`
- `KERNEL32!GetProcessHeap` at `0x1800224ab`
- `KERNEL32!GetProcessHeap` at `0x180022612`
- `KERNEL32!GetProcessHeap` at `0x180022650`
- `KERNEL32!GetProcessHeap` at `0x180022669`
- `KERNEL32!GetProcessHeap` at `0x1800224ab`
- `KERNEL32!GetProcessHeap` at `0x180022612`
- `KERNEL32!GetProcessHeap` at `0x180022650`
- `KERNEL32!GetProcessHeap` at `0x180022669`
- `KERNEL32!CreateFileW` at `0x180022474`
- `KERNEL32!CreateFileW` at `0x180022474`
- `KERNEL32!DeviceIoControl` at `0x18002258a`
- `KERNEL32!DeviceIoControl` at `0x18002258a`

## pseudocode

```c
__int64 __fastcall EnumNlmLocks(void *a1, unsigned int (*a2)(void *, unsigned __int16 *, struct _NLM_LOCKED_FILE *))
{
  unsigned int *v2; // rdi
  _DWORD *v3; // rsi
  HANDLE FileW; // rax
  void *v5; // r12
  unsigned int NlmClients; // eax
  DWORD LastError; // ebx
  char v8; // r15
  HANDLE ProcessHeap; // rax
  unsigned int i; // r13d
  __int64 v11; // r14
  unsigned __int16 *v12; // rax
  size_t v13; // r8
  DWORD v14; // eax
  int v15; // r12d
  struct _NLM_LOCKED_FILE *v16; // r14
  unsigned int v17; // eax
  void *v18; // r14
  HANDLE v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v25; // [rsp+50h] [rbp-B0h]
  void *v26; // [rsp+58h] [rbp-A8h]
  _DWORD InBuffer[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[1032]; // [rsp+68h] [rbp-98h] BYREF

  v26 = a1;
  v2 = 0;
  lpMem = 0;
  BytesReturned = 0;
  memset_0(InBuffer, 0, 0x40Cu);
  v3 = 0;
  FileW = CreateFileW(L"\\\\.\\NfsSvr", 0x80000000, 0, 0, 3u, 0x1000080u, 0);
  v25 = FileW;
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    NlmClients = GetNlmClients(FileW, (struct _NLM_LOCK_CLIENTS **)&lpMem);
    v2 = (unsigned int *)lpMem;
    LastError = NlmClients;
    if ( !NlmClients )
    {
      v8 = 0;
      ProcessHeap = GetProcessHeap();
      v3 = HeapAlloc(ProcessHeap, 8u, 0x1000u);
      if ( !v3 )
        LastError = 8;
      for ( i = 0; !v8 && !LastError && i < *v2; ++i )
      {
        v11 = 258LL * i;
        if ( v2[v11 + 1] >= 0x401 )
        {
          LastError = 13;
          break;
        }
        *((_BYTE *)&v2[v11 + 2] + v2[v11 + 1]) = 0;
        v12 = ConvertToWchar((char *)&v2[v11 + 2]);
        v13 = v2[v11 + 1];
        lpMem = v12;
        memcpy_0(v28, &v2[v11 + 2], v13);
        InBuffer[1] = v2[v11 + 1];
        InBuffer[0] = 0;
LABEL_11:
        memset_0(v3, 0, 0x1000u);
        LastError = 0;
        if ( DeviceIoControl(v5, 0xA0282018, InBuffer, 0x40Cu, v3, 0x1000u, &BytesReturned, 0)
          || (v14 = GetLastError(), LastError = v14, v14 == 234)
          || !v14 )
        {
          if ( BytesReturned >= 8 )
          {
            v15 = v3[1];
            v16 = (struct _NLM_LOCKED_FILE *)(v3 + 2);
            v17 = 0;
            while ( !v17 )
            {
              if ( !v15 )
                goto LABEL_21;
              v17 = EnumLocksCallBackFunc(v26, (unsigned __int16 *)lpMem, v16);
              if ( v17 == 1223 )
              {
                v8 = 1;
LABEL_21:
                InBuffer[0] += v3[1];
                if ( LastError == 234 && !v8 )
                {
                  v5 = v25;
                  goto LABEL_11;
                }
                break;
              }
              v16 = (struct _NLM_LOCKED_FILE *)((char *)v3 + *(unsigned int *)v16);
              --v15;
            }
          }
        }
        v18 = lpMem;
        if ( lpMem )
        {
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v18);
        }
        v5 = v25;
      }
    }
    CloseHandle(v5);
  }
  if ( v2 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v2);
  }
  if ( v3 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v3);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800223f8  push    rbp
0x1800223fa  push    rbx
0x1800223fb  push    rsi
0x1800223fc  push    rdi
0x1800223fd  push    r12
0x1800223ff  push    r13
0x180022401  push    r14
0x180022403  push    r15
0x180022405  lea     rbp, [rsp-388h]
0x18002240d  sub     rsp, 488h
0x180022414  mov     rax, cs:__security_cookie
0x18002241b  xor     rax, rsp
0x18002241e  mov     [rbp+3C0h+var_50], rax
0x180022425  mov     [rsp+4C0h+var_468], rcx
0x18002242a  xor     edi, edi
0x18002242c  lea     rcx, [rsp+4C0h+InBuffer]; void *
0x180022431  mov     [rsp+4C0h+lpMem], rdi
0x180022436  xor     edx, edx; Val
0x180022438  mov     [rsp+4C0h+BytesReturned], 0
0x180022440  mov     r8d, 40Ch; Size
0x180022446  call    memset_0
0x18002244b  xor     esi, esi
0x18002244d  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x180022454  mov     [rsp+4C0h+hTemplateFile], rsi; hTemplateFile
0x180022459  xor     r9d, r9d; lpSecurityAttributes
0x18002245c  mov     [rsp+4C0h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x180022464  xor     r8d, r8d; dwShareMode
0x180022467  mov     edx, 80000000h; dwDesiredAccess
0x18002246c  mov     [rsp+4C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180022474  call    cs:__imp_CreateFileW
0x18002247a  mov     [rsp+4C0h+var_470], rax
0x18002247f  mov     r12, rax
0x180022482  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022486  jz      loc_180022643
0x18002248c  lea     rdx, [rsp+4C0h+lpMem]; struct _NLM_LOCK_CLIENTS **
0x180022491  mov     rcx, rax; hDevice
0x180022494  call    ?GetNlmClients@@YAKPEAXPEAPEAU_NLM_LOCK_CLIENTS@@@Z; GetNlmClients(void *,_NLM_LOCK_CLIENTS * *)
0x180022499  mov     rdi, [rsp+4C0h+lpMem]
0x18002249e  mov     ebx, eax
0x1800224a0  test    eax, eax
0x1800224a2  jnz     loc_180022638
0x1800224a8  xor     r15b, r15b
0x1800224ab  call    cs:__imp_GetProcessHeap
0x1800224b1  lea     r14d, [rsi+8]
0x1800224b5  mov     r8d, 1000h; dwBytes
0x1800224bb  mov     rcx, rax; hHeap
0x1800224be  mov     edx, r14d; dwFlags
0x1800224c1  call    cs:__imp_HeapAlloc
0x1800224c7  test    rax, rax
0x1800224ca  mov     rsi, rax
0x1800224cd  cmovz   ebx, r14d
0x1800224d1  xor     r13d, r13d
0x1800224d4  test    r15b, r15b
0x1800224d7  jnz     loc_180022638
0x1800224dd  test    ebx, ebx
0x1800224df  jnz     loc_180022638
0x1800224e5  cmp     r13d, [rdi]
0x1800224e8  jnb     loc_180022638
0x1800224ee  mov     eax, r13d
0x1800224f1  imul    r14, rax, 408h
0x1800224f8  cmp     dword ptr [r14+rdi+4], 401h
0x180022501  jnb     loc_180022633
0x180022507  mov     eax, [r14+rdi+4]
0x18002250c  add     rax, r14
0x18002250f  mov     [rax+rdi+8], bl
0x180022513  lea     rbx, [r14+rdi]
0x180022517  lea     rcx, [rbx+8]; SrcBuf
0x18002251b  call    ?ConvertToWchar@@YAPEAGPEAD@Z; ConvertToWchar(char *)
0x180022520  mov     r8d, [r14+rdi+4]; Size
0x180022525  lea     rdx, [rbx+8]; Src
0x180022529  lea     rcx, [rsp+4C0h+var_458]; void *
0x18002252e  mov     [rsp+4C0h+lpMem], rax
0x180022533  call    memcpy_0
0x180022538  mov     ecx, [r14+rdi+4]
0x18002253d  mov     [rsp+4C0h+var_45C], ecx
0x180022541  mov     [rsp+4C0h+InBuffer], 0
0x180022549  mov     r14d, 1000h
0x18002254f  xor     edx, edx; Val
0x180022551  mov     r8d, r14d; Size
0x180022554  mov     rcx, rsi; void *
0x180022557  call    memset_0
0x18002255c  lea     rax, [rsp+4C0h+BytesReturned]
0x180022561  xor     ebx, ebx
0x180022563  mov     [rsp+4C0h+lpOverlapped], rbx; lpOverlapped
0x180022568  lea     r8, [rsp+4C0h+InBuffer]; lpInBuffer
0x18002256d  mov     [rsp+4C0h+hTemplateFile], rax; lpBytesReturned
0x180022572  mov     r9d, 40Ch; nInBufferSize
0x180022578  mov     [rsp+4C0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18002257d  mov     edx, 0A0282018h; dwIoControlCode
0x180022582  mov     rcx, r12; hDevice
0x180022585  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rsi; lpOutBuffer
0x18002258a  call    cs:__imp_DeviceIoControl
0x180022590  test    eax, eax
0x180022592  jnz     short loc_1800225A7
0x180022594  call    cs:__imp_GetLastError
0x18002259a  mov     ebx, eax
0x18002259c  cmp     eax, 0EAh
0x1800225a1  jz      short loc_1800225A7
0x1800225a3  test    eax, eax
0x1800225a5  jnz     short loc_180022608
0x1800225a7  cmp     [rsp+4C0h+BytesReturned], 8
0x1800225ac  jb      short loc_180022608
0x1800225ae  mov     r12d, [rsi+4]
0x1800225b2  lea     r14, [rsi+8]
0x1800225b6  xor     eax, eax
0x1800225b8  test    eax, eax
0x1800225ba  jnz     short loc_180022608
0x1800225bc  test    r12d, r12d
0x1800225bf  jz      short loc_1800225E8
0x1800225c1  mov     rdx, [rsp+4C0h+lpMem]; unsigned __int16 *
0x1800225c6  mov     r8, r14; struct _NLM_LOCKED_FILE *
0x1800225c9  mov     rcx, [rsp+4C0h+var_468]; void *
0x1800225ce  call    ?EnumLocksCallBackFunc@@YAKPEAXPEAGPEAU_NLM_LOCKED_FILE@@@Z; EnumLocksCallBackFunc(void *,ushort *,_NLM_LOCKED_FILE *)
0x1800225d3  cmp     eax, 4C7h
0x1800225d8  jz      short loc_1800225E5
0x1800225da  mov     r14d, [r14]
0x1800225dd  add     r14, rsi
0x1800225e0  dec     r12d
0x1800225e3  jmp     short loc_1800225B8
0x1800225e5  mov     r15b, 1
0x1800225e8  mov     eax, [rsi+4]
0x1800225eb  mov     cl, r15b
0x1800225ee  add     [rsp+4C0h+InBuffer], eax
0x1800225f2  cmp     ebx, 0EAh
0x1800225f8  jnz     short loc_180022608
0x1800225fa  test    cl, cl
0x1800225fc  jnz     short loc_180022608
0x1800225fe  mov     r12, [rsp+4C0h+var_470]
0x180022603  jmp     loc_180022549
0x180022608  mov     r14, [rsp+4C0h+lpMem]
0x18002260d  test    r14, r14
0x180022610  jz      short loc_180022626
0x180022612  call    cs:__imp_GetProcessHeap
0x180022618  mov     r8, r14; lpMem
0x18002261b  xor     edx, edx; dwFlags
0x18002261d  mov     rcx, rax; hHeap
0x180022620  call    cs:__imp_HeapFree
0x180022626  mov     r12, [rsp+4C0h+var_470]
0x18002262b  inc     r13d
0x18002262e  jmp     loc_1800224D4
0x180022633  mov     ebx, 0Dh
0x180022638  mov     rcx, r12; hObject
0x18002263b  call    cs:__imp_CloseHandle
0x180022641  jmp     short loc_18002264B
0x180022643  call    cs:__imp_GetLastError
0x180022649  mov     ebx, eax
0x18002264b  test    rdi, rdi
0x18002264e  jz      short loc_180022664
0x180022650  call    cs:__imp_GetProcessHeap
0x180022656  mov     r8, rdi; lpMem
0x180022659  xor     edx, edx; dwFlags
0x18002265b  mov     rcx, rax; hHeap
0x18002265e  call    cs:__imp_HeapFree
0x180022664  test    rsi, rsi
0x180022667  jz      short loc_18002267D
0x180022669  call    cs:__imp_GetProcessHeap
0x18002266f  mov     r8, rsi; lpMem
0x180022672  xor     edx, edx; dwFlags
0x180022674  mov     rcx, rax; hHeap
0x180022677  call    cs:__imp_HeapFree
0x18002267d  mov     eax, ebx
0x18002267f  mov     rcx, [rbp+3C0h+var_50]
0x180022686  xor     rcx, rsp; StackCookie
0x180022689  call    __security_check_cookie
0x18002268e  add     rsp, 488h
0x180022695  pop     r15
0x180022697  pop     r14
0x180022699  pop     r13
0x18002269b  pop     r12
0x18002269d  pop     rdi
0x18002269e  pop     rsi
0x18002269f  pop     rbx
0x1800226a0  pop     rbp
0x1800226a1  retn
```
