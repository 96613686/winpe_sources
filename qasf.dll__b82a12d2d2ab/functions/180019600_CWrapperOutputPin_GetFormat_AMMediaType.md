# CWrapperOutputPin::GetFormat(_AMMediaType * *)

- ea: `0x180019600`
- end: `0x180019763`
- name: `?GetFormat@CWrapperOutputPin@@UEAAJPEAPEAU_AMMediaType@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(CWrapperOutputPin *__hidden this, struct _AMMediaType **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x180001460`
- `0x180001cfc`
- `0x180019600`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180019643`
- `KERNEL32!EnterCriticalSection` at `0x180019643`
- `KERNEL32!LeaveCriticalSection` at `0x180019740`
- `KERNEL32!LeaveCriticalSection` at `0x180019740`
- `ole32!CoTaskMemAlloc` at `0x1800196e9`
- `ole32!CoTaskMemAlloc` at `0x1800196e9`
- `ole32!CoTaskMemFree` at `0x180019728`
- `ole32!CoTaskMemFree` at `0x180019728`

## pseudocode

```c
__int64 __fastcall CWrapperOutputPin::GetFormat(CWrapperOutputPin *this, LPVOID *a2)
{
  char *v5; // r14
  __int64 v6; // rbx
  __int64 v7; // r9
  unsigned int v8; // r8d
  __int64 v9; // rdx
  void (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // r9
  __int64 v11; // rcx
  unsigned int v12; // edi
  struct _AMMediaType *v13; // rax
  __int64 v14; // [rsp+20h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = (char *)this - 232;
  v6 = *((_QWORD *)this - 19);
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 224));
  v7 = *((_QWORD *)this - 19);
  v8 = *(_DWORD *)(v7 + 192);
  if ( v8 )
  {
    v9 = 0;
    while ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 136) + 8 * v9) + 48LL) )
    {
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= v8 )
        goto LABEL_7;
    }
    v12 = -2147220983;
  }
  else
  {
LABEL_7:
    if ( *((_BYTE *)this + 191) )
    {
      v10 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(v7 + 160);
      v11 = 0;
      v14 = 0;
      if ( v10 )
      {
        (**v10)(v10, &IID_IAMStreamConfig, &v14);
        v11 = v14;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v11 + 32LL))(v11, a2);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    else
    {
      v13 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
      *a2 = v13;
      if ( v13 )
      {
        memset_0(v13, 0, sizeof(struct _AMMediaType));
        v12 = (*(__int64 (__fastcall **)(char *, _QWORD, LPVOID))(*(_QWORD *)v5 + 104LL))(v5, 0, *a2);
        if ( v12 )
        {
          CoTaskMemFree(*a2);
          *a2 = 0;
        }
        else
        {
          v12 = 0;
        }
      }
      else
      {
        v12 = -2147024882;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 224));
  return v12;
}

```

## disassembly

```asm
0x180019600  mov     [rsp+arg_10], rbx
0x180019605  push    rsi
0x180019606  push    rdi
0x180019607  push    r14
0x180019609  sub     rsp, 30h
0x18001960d  mov     rax, cs:__security_cookie
0x180019614  xor     rax, rsp
0x180019617  mov     [rsp+48h+var_20], rax
0x18001961c  mov     rsi, rdx
0x18001961f  mov     rdi, rcx
0x180019622  test    rdx, rdx
0x180019625  jnz     short loc_180019631
0x180019627  mov     eax, 80004003h
0x18001962c  jmp     loc_180019748
0x180019631  lea     r14, [rcx-0E8h]
0x180019638  mov     rbx, [r14+50h]
0x18001963c  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180019643  call    cs:__imp_EnterCriticalSection
0x180019649  mov     r9, [rdi-98h]
0x180019650  mov     r8d, [r9+0C0h]
0x180019657  test    r8d, r8d
0x18001965a  jz      short loc_180019677
0x18001965c  mov     r10, [r9+88h]
0x180019663  xor     edx, edx
0x180019665  mov     rcx, [r10+rdx*8]
0x180019669  cmp     qword ptr [rcx+30h], 0
0x18001966e  jz      short loc_1800196DB
0x180019670  inc     edx
0x180019672  cmp     edx, r8d
0x180019675  jb      short loc_180019665
0x180019677  cmp     byte ptr [rdi+0BFh], 0
0x18001967e  jz      short loc_1800196E2
0x180019680  mov     r9, [r9+0A0h]
0x180019687  xor     ecx, ecx
0x180019689  mov     [rsp+48h+var_28], rcx
0x18001968e  test    r9, r9
0x180019691  jz      short loc_1800196B2
0x180019693  mov     rax, [r9]
0x180019696  lea     r8, [rsp+48h+var_28]
0x18001969b  lea     rdx, IID_IAMStreamConfig
0x1800196a2  mov     rcx, r9
0x1800196a5  mov     rax, [rax]
0x1800196a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196ad  mov     rcx, [rsp+48h+var_28]
0x1800196b2  mov     rax, [rcx]
0x1800196b5  mov     rdx, rsi
0x1800196b8  mov     rax, [rax+20h]
0x1800196bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196c1  mov     rcx, [rsp+48h+var_28]
0x1800196c6  mov     edi, eax
0x1800196c8  test    rcx, rcx
0x1800196cb  jz      short loc_180019739
0x1800196cd  mov     rdx, [rcx]
0x1800196d0  mov     rax, [rdx+10h]
0x1800196d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196d9  jmp     short loc_180019739
0x1800196db  mov     edi, 80040209h
0x1800196e0  jmp     short loc_180019739
0x1800196e2  mov     edi, 58h ; 'X'
0x1800196e7  mov     ecx, edi; cb
0x1800196e9  call    cs:__imp_CoTaskMemAlloc
0x1800196ef  mov     [rsi], rax
0x1800196f2  test    rax, rax
0x1800196f5  jnz     short loc_1800196FE
0x1800196f7  mov     edi, 8007000Eh
0x1800196fc  jmp     short loc_180019739
0x1800196fe  mov     r8, rdi; Size
0x180019701  xor     edx, edx; Val
0x180019703  mov     rcx, rax; void *
0x180019706  call    memset_0
0x18001970b  mov     rax, [r14]
0x18001970e  xor     edx, edx
0x180019710  mov     r8, [rsi]
0x180019713  mov     rcx, r14
0x180019716  mov     rax, [rax+68h]
0x18001971a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001971f  mov     edi, eax
0x180019721  test    eax, eax
0x180019723  jz      short loc_180019737
0x180019725  mov     rcx, [rsi]; pv
0x180019728  call    cs:__imp_CoTaskMemFree
0x18001972e  mov     qword ptr [rsi], 0
0x180019735  jmp     short loc_180019739
0x180019737  xor     edi, edi
0x180019739  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180019740  call    cs:__imp_LeaveCriticalSection
0x180019746  mov     eax, edi
0x180019748  mov     rcx, [rsp+48h+var_20]
0x18001974d  xor     rcx, rsp; StackCookie
0x180019750  call    __security_check_cookie
0x180019755  mov     rbx, [rsp+48h+arg_10]
0x18001975a  add     rsp, 30h
0x18001975e  pop     r14
0x180019760  pop     rdi
0x180019761  pop     rsi
0x180019762  retn
```
