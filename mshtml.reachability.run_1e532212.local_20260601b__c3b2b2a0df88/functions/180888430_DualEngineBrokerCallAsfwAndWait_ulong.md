# _DualEngineBrokerCallAsfwAndWait(ulong)

- ea: `0x180888430`
- end: `0x180888762`
- name: `?_DualEngineBrokerCallAsfwAndWait@@YA_NK@Z`
- size: `818`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180888900`

## callees

- `0x1804e4c1c`
- `0x180888430`
- `0x180888770`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18088845a`
- `KERNEL32!GetCurrentThreadId` at `0x18088845a`
- `KERNEL32!CloseHandle` at `0x180888728`
- `KERNEL32!CloseHandle` at `0x180888728`
- `USER32!AllowSetForegroundWindow` at `0x180888502`
- `USER32!AllowSetForegroundWindow` at `0x180888627`
- `USER32!AllowSetForegroundWindow` at `0x180888502`
- `USER32!AllowSetForegroundWindow` at `0x180888627`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808884c5`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808885ea`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808884c5`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808885ea`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x180888718`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x180888718`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180888589`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808886ae`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180888589`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808886ae`

## pseudocode

```c
__int64 __fastcall _DualEngineBrokerCallAsfwAndWait(unsigned int a1)
{
  unsigned __int8 v2; // di
  DWORD CurrentThreadId; // eax
  DWORD v4; // ecx
  int v5; // ebx
  void (__fastcall *v6)(__int64, __int128 *); // rbx
  int v7; // ebx
  void (*v8)(void); // rax
  DWORD v9; // ecx
  int v10; // ebx
  void (__fastcall *v11)(__int64, __int128 *); // rbx
  DWORD dwProcessId; // [rsp+30h] [rbp-79h] BYREF
  __int64 v14; // [rsp+38h] [rbp-71h] BYREF
  struct IEUserBroker *v15; // [rsp+40h] [rbp-69h] BYREF
  DWORD dwindex; // [rsp+48h] [rbp-61h] BYREF
  __int128 v17; // [rsp+50h] [rbp-59h] BYREF
  HANDLE pHandles; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 v19[64]; // [rsp+70h] [rbp-39h] BYREF

  v2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( (int)StringCchPrintfW(v19, 0x40u, L"_%d", CurrentThreadId) >= 0 )
  {
    pHandles = _DualEngineCreateWaitEvent(a1, 1, v19);
    if ( pHandles )
    {
      dwindex = 0;
      if ( a1 == 5153 )
      {
        v14 = 0;
        v15 = 0;
        if ( (int)CoCreateUserBroker(&v15) < 0 )
          goto LABEL_21;
        dwProcessId = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v15 + 24LL))(
          v15,
          0,
          0,
          &dwProcessId);
        v4 = -1;
        if ( dwProcessId )
          v4 = dwProcessId;
        AllowSetForegroundWindow(v4);
        *(_QWORD *)&v17 = 0;
        v5 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v15 + 48LL))(
               v15,
               &CLSID_CShdocvwBroker,
               &IID_IUnknown,
               &v17);
        if ( v5 >= 0 )
        {
          v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v17)(
                 v17,
                 &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                 &v14);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 16LL))(v17);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v5 < 0 )
          goto LABEL_21;
        v6 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v14 + 56LL);
        v17 = *(_OWORD *)GlobalThreadState();
        v6(v14, &v17);
        v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v14 + 80LL))(v14, v19);
        v8 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
      }
      else
      {
        if ( a1 != 5154 )
          goto LABEL_21;
        v14 = 0;
        v15 = 0;
        if ( (int)CoCreateUserBroker(&v15) < 0 )
          goto LABEL_21;
        dwProcessId = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v15 + 24LL))(
          v15,
          0,
          0,
          &dwProcessId);
        v9 = -1;
        if ( dwProcessId )
          v9 = dwProcessId;
        AllowSetForegroundWindow(v9);
        *(_QWORD *)&v17 = 0;
        v10 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v15 + 48LL))(
                v15,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v17);
        if ( v10 >= 0 )
        {
          v10 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v17)(
                  v17,
                  &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                  &v14);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 16LL))(v17);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v10 < 0 )
          goto LABEL_21;
        v11 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v14 + 56LL);
        v17 = *(_OWORD *)GlobalThreadState();
        v11(v14, &v17);
        v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v14 + 88LL))(v14, v19);
        v8 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
      }
      v8();
      if ( v7 >= 0 )
      {
        v2 = 1;
        CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
      }
LABEL_21:
      CloseHandle(pHandles);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180888430  mov     [rsp-8+arg_10], rbx
0x180888435  mov     [rsp-8+arg_18], rdi
0x18088843a  push    rbp
0x18088843b  lea     rbp, [rsp-57h]
0x180888440  sub     rsp, 100h
0x180888447  mov     rax, cs:__security_cookie
0x18088844e  xor     rax, rsp
0x180888451  mov     [rbp+57h+var_10], rax
0x180888455  mov     ebx, ecx
0x180888457  xor     dil, dil
0x18088845a  call    cs:__imp_GetCurrentThreadId
0x180888461  nop     dword ptr [rax+rax+00h]
0x180888466  lea     r8, aD_0; "_%d"
0x18088846d  mov     edx, 40h ; '@'; unsigned __int64
0x180888472  mov     r9d, eax
0x180888475  lea     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180888479  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18088847e  test    eax, eax
0x180888480  js      loc_18088873C
0x180888486  lea     r8, [rbp+57h+var_90]; unsigned __int16 *
0x18088848a  mov     dl, 1; bool
0x18088848c  mov     ecx, ebx; unsigned int
0x18088848e  call    ?_DualEngineCreateWaitEvent@@YAPEAXK_NPEBG@Z; _DualEngineCreateWaitEvent(ulong,bool,ushort const *)
0x180888493  mov     [rbp+57h+pHandles], rax
0x180888497  test    rax, rax
0x18088849a  jz      loc_18088873C
0x1808884a0  mov     [rsp+100h+arg_8], rsi
0x1808884a8  xor     esi, esi
0x1808884aa  mov     [rbp+57h+dwindex], esi
0x1808884ad  cmp     ebx, 1421h
0x1808884b3  jnz     loc_1808885D2
0x1808884b9  lea     rcx, [rbp+57h+var_C0]
0x1808884bd  mov     [rbp+57h+var_C8], rsi
0x1808884c1  mov     [rbp+57h+var_C0], rsi
0x1808884c5  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1808884cc  nop     dword ptr [rax+rax+00h]
0x1808884d1  test    eax, eax
0x1808884d3  js      loc_180888724
0x1808884d9  mov     rcx, [rbp+57h+var_C0]
0x1808884dd  lea     r9, [rbp+57h+dwProcessId]
0x1808884e1  mov     [rbp+57h+dwProcessId], esi
0x1808884e4  xor     r8d, r8d
0x1808884e7  xor     edx, edx
0x1808884e9  mov     rax, [rcx]
0x1808884ec  mov     rax, [rax+18h]
0x1808884f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808884f5  mov     eax, [rbp+57h+dwProcessId]
0x1808884f8  mov     ecx, 0FFFFFFFFh
0x1808884fd  test    eax, eax
0x1808884ff  cmovnz  ecx, eax; dwProcessId
0x180888502  call    cs:__imp_AllowSetForegroundWindow
0x180888509  nop     dword ptr [rax+rax+00h]
0x18088850e  mov     rcx, [rbp+57h+var_C0]
0x180888512  lea     r9, [rbp+57h+var_B0]
0x180888516  mov     qword ptr [rbp+57h+var_B0], rsi
0x18088851a  lea     r8, IID_IUnknown
0x180888521  lea     rdx, CLSID_CShdocvwBroker
0x180888528  mov     rax, [rcx]
0x18088852b  mov     rax, [rax+30h]
0x18088852f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180888534  mov     ebx, eax
0x180888536  test    eax, eax
0x180888538  js      short loc_180888566
0x18088853a  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18088853e  lea     r8, [rbp+57h+var_C8]
0x180888542  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180888549  mov     rax, [rcx]
0x18088854c  mov     rax, [rax]
0x18088854f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180888554  mov     rcx, qword ptr [rbp+57h+var_B0]
0x180888558  mov     ebx, eax
0x18088855a  mov     rax, [rcx]
0x18088855d  mov     rax, [rax+10h]
0x180888561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180888566  mov     rcx, [rbp+57h+var_C0]
0x18088856a  mov     rax, [rcx]
0x18088856d  mov     rax, [rax+10h]
0x180888571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180888576  test    ebx, ebx
0x180888578  js      loc_180888724
0x18088857e  mov     rax, [rbp+57h+var_C8]
0x180888582  mov     rcx, [rax]
0x180888585  mov     rbx, [rcx+38h]
0x180888589  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180888590  nop     dword ptr [rax+rax+00h]
0x180888595  mov     rcx, [rbp+57h+var_C8]
0x180888599  lea     rdx, [rbp+57h+var_B0]
0x18088859d  movups  xmm0, xmmword ptr [rax]
0x1808885a0  mov     rax, rbx
0x1808885a3  movaps  [rbp+57h+var_B0], xmm0
0x1808885a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808885ac  mov     rcx, [rbp+57h+var_C8]
0x1808885b0  lea     rdx, [rbp+57h+var_90]
0x1808885b4  mov     rax, [rcx]
0x1808885b7  mov     rax, [rax+50h]
0x1808885bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808885c0  mov     rcx, [rbp+57h+var_C8]
0x1808885c4  mov     ebx, eax
0x1808885c6  mov     r8, [rcx]
0x1808885c9  mov     rax, [r8+10h]
0x1808885cd  jmp     loc_1808886F2
0x1808885d2  cmp     ebx, 1422h
0x1808885d8  jnz     loc_180888724
0x1808885de  lea     rcx, [rbp+57h+var_C0]
0x1808885e2  mov     [rbp+57h+var_C8], rsi
0x1808885e6  mov     [rbp+57h+var_C0], rsi
0x1808885ea  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1808885f1  nop     dword ptr [rax+rax+00h]
0x1808885f6  test    eax, eax
0x1808885f8  js      loc_180888724
0x1808885fe  mov     rcx, [rbp+57h+var_C0]
0x180888602  lea     r9, [rbp+57h+dwProcessId]
0x180888606  mov     [rbp+57h+dwProcessId], esi
0x180888609  xor     r8d, r8d
0x18088860c  xor     edx, edx
0x18088860e  mov     rax, [rcx]
0x180888611  mov     rax, [rax+18h]
0x180888615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18088861a  mov     eax, [rbp+57h+dwProcessId]
0x18088861d  mov     ecx, 0FFFFFFFFh
0x180888622  test    eax, eax
0x180888624  cmovnz  ecx, eax; dwProcessId
0x180888627  call    cs:__imp_AllowSetForegroundWindow
0x18088862e  nop     dword ptr [rax+rax+00h]
0x180888633  mov     rcx, [rbp+57h+var_C0]
0x180888637  lea     r9, [rbp+57h+var_B0]
0x18088863b  mov     qword ptr [rbp+57h+var_B0], rsi
0x18088863f  lea     r8, IID_IUnknown
0x180888646  lea     rdx, CLSID_CShdocvwBroker
0x18088864d  mov     rax, [rcx]
0x180888650  mov     rax, [rax+30h]
0x180888654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180888659  mov     ebx, eax
0x18088865b  test    eax, eax
0x18088865d  js      short loc_18088868B
0x18088865f  mov     rcx, qword ptr [rbp+57h+var_B0]
0x180888663  lea     r8, [rbp+57h+var_C8]
0x180888667  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x18088866e  mov     rax, [rcx]
0x180888671  mov     rax, [rax]
0x180888674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180888679  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18088867d  mov     ebx, eax
0x18088867f  mov     rax, [rcx]
0x180888682  mov     rax, [rax+10h]
0x180888686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18088868b  mov     rcx, [rbp+57h+var_C0]
0x18088868f  mov     rax, [rcx]
0x180888692  mov     rax, [rax+10h]
0x180888696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18088869b  test    ebx, ebx
0x18088869d  js      loc_180888724
0x1808886a3  mov     rax, [rbp+57h+var_C8]
0x1808886a7  mov     rcx, [rax]
0x1808886aa  mov     rbx, [rcx+38h]
0x1808886ae  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808886b5  nop     dword ptr [rax+rax+00h]
0x1808886ba  mov     rcx, [rbp+57h+var_C8]
0x1808886be  lea     rdx, [rbp+57h+var_B0]
0x1808886c2  movups  xmm0, xmmword ptr [rax]
0x1808886c5  mov     rax, rbx
0x1808886c8  movaps  [rbp+57h+var_B0], xmm0
0x1808886cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808886d1  mov     rcx, [rbp+57h+var_C8]
0x1808886d5  lea     rdx, [rbp+57h+var_90]
0x1808886d9  mov     rax, [rcx]
0x1808886dc  mov     rax, [rax+58h]
0x1808886e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808886e5  mov     rcx, [rbp+57h+var_C8]
0x1808886e9  mov     ebx, eax
0x1808886eb  mov     rdx, [rcx]
0x1808886ee  mov     rax, [rdx+10h]
0x1808886f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808886f7  test    ebx, ebx
0x1808886f9  js      short loc_180888724
0x1808886fb  lea     rax, [rbp+57h+dwindex]
0x1808886ff  mov     r8d, 1; cHandles
0x180888705  lea     r9, [rbp+57h+pHandles]; pHandles
0x180888709  mov     [rsp+100h+lpdwindex], rax; lpdwindex
0x18088870e  mov     edx, 0FFFFFFFFh; dwTimeout
0x180888713  xor     ecx, ecx; dwFlags
0x180888715  mov     dil, 1
0x180888718  call    cs:__imp_CoWaitForMultipleHandles
0x18088871f  nop     dword ptr [rax+rax+00h]
0x180888724  mov     rcx, [rbp+57h+pHandles]; hObject
0x180888728  call    cs:__imp_CloseHandle
0x18088872f  nop     dword ptr [rax+rax+00h]
0x180888734  mov     rsi, [rsp+100h+arg_8]
0x18088873c  movzx   eax, dil
0x180888740  mov     rcx, [rbp+57h+var_10]
0x180888744  xor     rcx, rsp; StackCookie
0x180888747  call    __security_check_cookie
0x18088874c  lea     r11, [rsp+100h+var_s0]
0x180888754  mov     rbx, [r11+20h]
0x180888758  mov     rdi, [r11+28h]
0x18088875c  mov     rsp, r11
0x18088875f  pop     rbp
0x180888760  retn
```
