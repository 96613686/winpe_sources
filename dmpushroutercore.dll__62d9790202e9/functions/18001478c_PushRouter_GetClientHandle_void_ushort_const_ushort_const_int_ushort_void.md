# PushRouter::GetClientHandle(void *,ushort const *,ushort const *,int,ushort * *,void * *)

- ea: `0x18001478c`
- end: `0x180014a50`
- name: `?GetClientHandle@PushRouter@@QEAAJPEAXPEBG1HPEAPEAGPEAPEAX@Z`
- size: `708`
- prototype: `__int64 __fastcall(PushRouter *this, void *, const unsigned __int16 *, const unsigned __int16 *, DWORD Pid, unsigned __int16 **, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1800105a0`

## callees

- `0x180003a14`
- `0x1800060b4`
- `0x18000c504`
- `0x180012860`
- `0x180013cdc`
- `0x180014468`
- `0x18001478c`
- `0x180017cec`
- `0x180018060`
- `0x180036338`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001495a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001495a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001497b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001497b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800149cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800149cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a0f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001496d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001496d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800149a0`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800149a0`

## pseudocode

```c
__int64 __fastcall PushRouter::GetClientHandle(
        PushRouter *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD Pid,
        unsigned __int16 **a6,
        void **a7)
{
  PushRouter *v8; // r14
  struct IPersistStore *v9; // r15
  signed int ExactRegisteredPC; // ebx
  struct PushClient *ExistingClient; // rsi
  struct PushClient *v12; // r14
  struct PushClient *v13; // rax
  unsigned __int16 *v14; // rdi
  __int64 v15; // rax
  unsigned __int16 *v16; // rcx
  __int64 v17; // rdx
  unsigned __int16 *v18; // r8
  unsigned __int16 v19; // r9
  unsigned __int16 *v20; // rcx
  const struct std::nothrow_t *v21; // rdx
  DWORD v22; // r8d
  DWORD v23; // ecx
  const struct std::nothrow_t *v24; // rdx
  HANDLE v25; // rbx
  signed int LastError; // eax
  void *v27; // rcx
  struct IPersistStore *v29; // [rsp+20h] [rbp-20h] BYREF
  HLOCAL v30; // [rsp+28h] [rbp-18h] BYREF
  struct PushClient *v31[2]; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+30h] BYREF

  v8 = g_pPushRouter;
  hMem = 0;
  v30 = 0;
  v9 = 0;
  v29 = 0;
  Pid = 0;
  ExactRegisteredPC = FindExactRegisteredPC(a3, a4, (unsigned __int16 **)&hMem, (unsigned __int16 **)&v30);
  if ( ExactRegisteredPC < 0 )
    goto LABEL_37;
  if ( !hMem )
  {
    ExactRegisteredPC = -2142044156;
    goto LABEL_37;
  }
  ExistingClient = PushRouter::FindExistingClient(v8, (const unsigned __int16 *)hMem);
  v31[0] = ExistingClient;
  if ( ExistingClient )
  {
    if ( *((_DWORD *)ExistingClient + 10) )
    {
      ExactRegisteredPC = -2142044159;
      goto LABEL_37;
    }
    v12 = ExistingClient;
    goto LABEL_35;
  }
  v13 = (struct PushClient *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
  v14 = (unsigned __int16 *)v13;
  v31[1] = v13;
  if ( !v13 )
  {
    ExactRegisteredPC = -2147024882;
    goto LABEL_37;
  }
  *(_WORD *)v13 = 0;
  v15 = 2147483646;
  v16 = *(unsigned __int16 **)v8;
  v17 = 260;
  v18 = v14;
  do
  {
    if ( !v15 )
      break;
    v19 = *v16;
    if ( !*v16 )
      break;
    ++v16;
    *v18++ = v19;
    --v15;
    --v17;
  }
  while ( v17 );
  ExactRegisteredPC = v17 == 0 ? 0x8007007A : 0;
  v20 = v18 - 1;
  if ( v17 )
    v20 = v18;
  *v20 = 0;
  if ( !v17 )
    goto LABEL_17;
  ExactRegisteredPC = StringCchCatW(v14, 0x104u, L"\\");
  if ( ExactRegisteredPC < 0 )
    goto LABEL_17;
  ExactRegisteredPC = StringCchCatW(v14, 0x104u, (const unsigned __int16 *)v30);
  if ( ExactRegisteredPC < 0 )
    goto LABEL_17;
  ExactRegisteredPC = StringCchCatW(v14, 0x104u, aQueue);
  if ( ExactRegisteredPC < 0 )
    goto LABEL_17;
  ExactRegisteredPC = PersistXmlStore::CreatePersistXmlStore(v14, &v29);
  if ( ExactRegisteredPC < 0 )
  {
    operator delete(v14, v21);
    v9 = v29;
    goto LABEL_37;
  }
  v9 = v29;
  ExactRegisteredPC = PushClient::CreateClient((const unsigned __int16 *)hMem, v29, v31);
  if ( ExactRegisteredPC < 0 )
  {
LABEL_17:
    operator delete(v14, (const struct std::nothrow_t *)v17);
    goto LABEL_37;
  }
  v9 = 0;
  ExistingClient = v31[0];
  CTList<PushClient>::AddHead((char *)v8 + 24, v31[0]);
  if ( !a2 )
  {
    Pid = GetCurrentProcessId();
    v22 = Pid;
    v23 = 1024;
    goto LABEL_26;
  }
  if ( I_RpcBindingInqLocalClientPID(a2, &Pid) )
  {
    ExactRegisteredPC = -2147418113;
    goto LABEL_17;
  }
  v22 = Pid;
  v23 = 0x1FFFFF;
LABEL_26:
  v25 = OpenProcess(v23, 0, v22);
  if ( !v25 )
  {
    LastError = GetLastError();
    ExactRegisteredPC = LastError;
    if ( LastError > 0 )
      ExactRegisteredPC = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  v12 = ExistingClient;
  v27 = (void *)*((_QWORD *)ExistingClient + 13);
  if ( v27 )
    CloseHandle(v27);
  *((_QWORD *)ExistingClient + 13) = v25;
  operator delete(v14, v24);
LABEL_35:
  ExactRegisteredPC = PushClient::AttachClient(ExistingClient, a2, a6);
  if ( ExactRegisteredPC >= 0 )
  {
    *((_DWORD *)v12 + 10) = 1;
    *a7 = ExistingClient;
  }
LABEL_37:
  LocalFree(hMem);
  LocalFree(v30);
  if ( v9 )
    (**(void (__fastcall ***)(struct IPersistStore *, __int64))v9)(v9, 1);
  CloseHandle(0);
  return (unsigned int)ExactRegisteredPC;
}

```

## disassembly

```asm
0x18001478c  mov     [rsp-28h+arg_8], rbx
0x180014791  mov     [rsp-28h+arg_10], rsi
0x180014796  mov     [rsp-28h+hMem], rcx
0x18001479b  push    rbp
0x18001479c  push    rdi
0x18001479d  push    r13
0x18001479f  push    r14
0x1800147a1  push    r15
0x1800147a3  mov     rbp, rsp
0x1800147a6  sub     rsp, 40h
0x1800147aa  mov     rax, r9
0x1800147ad  mov     rcx, r8; unsigned __int16 *
0x1800147b0  mov     r13, rdx
0x1800147b3  mov     r14, cs:?g_pPushRouter@@3PEAVPushRouter@@EA; PushRouter * g_pPushRouter
0x1800147ba  xor     esi, esi
0x1800147bc  mov     [rbp+hMem], rsi
0x1800147c0  mov     [rbp+var_18], rsi
0x1800147c4  mov     r15d, esi
0x1800147c7  mov     [rbp+var_20], rsi
0x1800147cb  mov     [rbp+Pid], esi
0x1800147ce  lea     r9, [rbp+var_18]; unsigned __int16 **
0x1800147d2  lea     r8, [rbp+hMem]; unsigned __int16 **
0x1800147d6  mov     rdx, rax; unsigned __int16 *
0x1800147d9  call    ?FindExactRegisteredPC@@YAJPEBG0PEAPEAG1@Z; FindExactRegisteredPC(ushort const *,ushort const *,ushort * *,ushort * *)
0x1800147de  mov     ebx, eax
0x1800147e0  test    eax, eax
0x1800147e2  js      loc_180014A01
0x1800147e8  cmp     [rbp+hMem], rsi
0x1800147ec  jnz     short loc_1800147F8
0x1800147ee  mov     ebx, 80530004h
0x1800147f3  jmp     loc_180014A01
0x1800147f8  mov     rdx, [rbp+hMem]; unsigned __int16 *
0x1800147fc  mov     rcx, r14; this
0x1800147ff  call    ?FindExistingClient@PushRouter@@AEAAPEAVPushClient@@PEBG@Z; PushRouter::FindExistingClient(ushort const *)
0x180014804  mov     rsi, rax
0x180014807  mov     [rbp+var_10], rax
0x18001480b  xor     eax, eax
0x18001480d  test    rsi, rsi
0x180014810  jz      short loc_180014829
0x180014812  cmp     [rsi+28h], eax
0x180014815  jz      short loc_180014821
0x180014817  mov     ebx, 80530001h
0x18001481c  jmp     loc_180014A01
0x180014821  mov     r14, rsi
0x180014824  jmp     loc_1800149DD
0x180014829  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014830  mov     ecx, 208h; unsigned __int64
0x180014835  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001483a  mov     rdi, rax
0x18001483d  mov     [rbp+var_8], rax
0x180014841  xor     esi, esi
0x180014843  test    rax, rax
0x180014846  jnz     short loc_180014852
0x180014848  mov     ebx, 8007000Eh
0x18001484d  jmp     loc_180014A01
0x180014852  mov     [rax], si
0x180014855  mov     eax, 7FFFFFFEh
0x18001485a  mov     rcx, [r14]
0x18001485d  mov     edx, 104h
0x180014862  mov     r8, rdi
0x180014865  test    rax, rax
0x180014868  jz      short loc_180014889
0x18001486a  movzx   r9d, word ptr [rcx]
0x18001486e  test    r9w, r9w
0x180014872  jz      short loc_180014889
0x180014874  add     rcx, 2
0x180014878  mov     [r8], r9w
0x18001487c  add     r8, 2
0x180014880  dec     rax
0x180014883  sub     rdx, 1; struct std::nothrow_t *
0x180014887  jnz     short loc_180014865
0x180014889  mov     rax, rdx
0x18001488c  neg     rax
0x18001488f  sbb     ebx, ebx
0x180014891  not     ebx
0x180014893  and     ebx, 8007007Ah
0x180014899  lea     rcx, [r8-2]
0x18001489d  test    rdx, rdx
0x1800148a0  cmovnz  rcx, r8
0x1800148a4  mov     [rcx], si
0x1800148a7  jnz     short loc_1800148B6
0x1800148a9  mov     rcx, rdi; void *
0x1800148ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800148b1  jmp     loc_180014A01
0x1800148b6  lea     r8, StringValue; "\\"
0x1800148bd  mov     edx, 104h; unsigned __int64
0x1800148c2  mov     rcx, rdi; unsigned __int16 *
0x1800148c5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800148ca  mov     ebx, eax
0x1800148cc  test    eax, eax
0x1800148ce  js      short loc_1800148A9
0x1800148d0  mov     r8, [rbp+var_18]; unsigned __int16 *
0x1800148d4  mov     edx, 104h; unsigned __int64
0x1800148d9  mov     rcx, rdi; unsigned __int16 *
0x1800148dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800148e1  mov     ebx, eax
0x1800148e3  test    eax, eax
0x1800148e5  js      short loc_1800148A9
0x1800148e7  lea     r8, aQueue; ".queue"
0x1800148ee  mov     edx, 104h; unsigned __int64
0x1800148f3  mov     rcx, rdi; unsigned __int16 *
0x1800148f6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800148fb  mov     ebx, eax
0x1800148fd  test    eax, eax
0x1800148ff  js      short loc_1800148A9
0x180014901  lea     rdx, [rbp+var_20]; struct IPersistStore **
0x180014905  mov     rcx, rdi; Src
0x180014908  call    ?CreatePersistXmlStore@PersistXmlStore@@SAJPEBGPEAPEAVIPersistStore@@@Z; PersistXmlStore::CreatePersistXmlStore(ushort const *,IPersistStore * *)
0x18001490d  mov     ebx, eax
0x18001490f  test    eax, eax
0x180014911  jns     short loc_180014924
0x180014913  mov     rcx, rdi; void *
0x180014916  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001491b  mov     r15, [rbp+var_20]
0x18001491f  jmp     loc_180014A01
0x180014924  lea     r8, [rbp+var_10]; struct PushClient **
0x180014928  mov     r15, [rbp+var_20]
0x18001492c  mov     rdx, r15; struct IPersistStore *
0x18001492f  mov     rcx, [rbp+hMem]; unsigned __int16 *
0x180014933  call    ?CreateClient@PushClient@@SAJPEBGPEAVIPersistStore@@PEAPEAV1@@Z; PushClient::CreateClient(ushort const *,IPersistStore *,PushClient * *)
0x180014938  mov     ebx, eax
0x18001493a  test    eax, eax
0x18001493c  js      loc_1800148A9
0x180014942  mov     r15, rsi
0x180014945  lea     rcx, [r14+18h]
0x180014949  mov     rsi, [rbp+var_10]
0x18001494d  mov     rdx, rsi
0x180014950  call    ?AddHead@?$CTList@VPushClient@@@@QEAAPEAVPushClient@@PEAV2@@Z; CTList<PushClient>::AddHead(PushClient *)
0x180014955  test    r13, r13
0x180014958  jnz     short loc_180014999
0x18001495a  call    cs:__imp_GetCurrentProcessId
0x180014960  mov     [rbp+Pid], eax
0x180014963  mov     r8d, eax; dwProcessId
0x180014966  mov     ecx, 400h; dwDesiredAccess
0x18001496b  xor     edx, edx; bInheritHandle
0x18001496d  call    cs:__imp_OpenProcess
0x180014973  mov     rbx, rax
0x180014976  test    rax, rax
0x180014979  jnz     short loc_1800149BF
0x18001497b  call    cs:__imp_GetLastError
0x180014981  mov     ebx, eax
0x180014983  test    eax, eax
0x180014985  jle     loc_1800148A9
0x18001498b  movzx   ebx, ax
0x18001498e  or      ebx, 80070000h
0x180014994  jmp     loc_1800148A9
0x180014999  lea     rdx, [rbp+Pid]; Pid
0x18001499d  mov     rcx, r13; Binding
0x1800149a0  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800149a6  test    eax, eax
0x1800149a8  jz      short loc_1800149B4
0x1800149aa  mov     ebx, 8000FFFFh
0x1800149af  jmp     loc_1800148A9
0x1800149b4  mov     r8d, [rbp+Pid]
0x1800149b8  mov     ecx, 1FFFFFh
0x1800149bd  jmp     short loc_18001496B
0x1800149bf  mov     r14, rsi
0x1800149c2  mov     rcx, [rsi+68h]; hObject
0x1800149c6  test    rcx, rcx
0x1800149c9  jz      short loc_1800149D1
0x1800149cb  call    cs:__imp_CloseHandle
0x1800149d1  mov     [rsi+68h], rbx
0x1800149d5  mov     rcx, rdi; void *
0x1800149d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800149dd  mov     r8, [rbp+arg_28]; unsigned __int16 **
0x1800149e1  mov     rdx, r13; void *
0x1800149e4  mov     rcx, rsi; this
0x1800149e7  call    ?AttachClient@PushClient@@QEAAJPEAXPEAPEAG@Z; PushClient::AttachClient(void *,ushort * *)
0x1800149ec  mov     ebx, eax
0x1800149ee  test    eax, eax
0x1800149f0  js      short loc_180014A01
0x1800149f2  mov     dword ptr [r14+28h], 1
0x1800149fa  mov     rax, [rbp+arg_30]
0x1800149fe  mov     [rax], rsi
0x180014a01  mov     rcx, [rbp+hMem]; hMem
0x180014a05  call    cs:__imp_LocalFree
0x180014a0b  mov     rcx, [rbp+var_18]; hMem
0x180014a0f  call    cs:__imp_LocalFree
0x180014a15  test    r15, r15
0x180014a18  jz      short loc_180014A2D
0x180014a1a  mov     rax, [r15]
0x180014a1d  mov     edx, 1
0x180014a22  mov     rcx, r15
0x180014a25  mov     rax, [rax]
0x180014a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a2d  xor     ecx, ecx; hObject
0x180014a2f  call    cs:__imp_CloseHandle
0x180014a35  mov     eax, ebx
0x180014a37  lea     r11, [rsp+40h+var_s0]
0x180014a3c  mov     rbx, [r11+38h]
0x180014a40  mov     rsi, [r11+40h]
0x180014a44  mov     rsp, r11
0x180014a47  pop     r15
0x180014a49  pop     r14
0x180014a4b  pop     r13
0x180014a4d  pop     rdi
0x180014a4e  pop     rbp
0x180014a4f  retn
```
