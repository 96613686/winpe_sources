# CallDiagFunctionWithCOMTimeout(tagDiagThreadContext *)

- ea: `0x180010578`
- end: `0x180010758`
- name: `?CallDiagFunctionWithCOMTimeout@@YAJPEAUtagDiagThreadContext@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(struct tagDiagThreadContext *lpParameter)`
- caller_count: `24`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800104b0`
- `0x180010760`
- `0x1800107d0`
- `0x180010b60`
- `0x180010be0`
- `0x180010c60`
- `0x180010ce0`
- `0x180010d60`
- `0x180010de0`
- `0x180010e60`
- `0x180010ee0`
- `0x180010f60`
- `0x180010ff0`
- `0x180011070`
- `0x180011100`
- `0x180011180`
- `0x180011208`
- `0x180011298`
- `0x180011320`
- `0x1800113b0`
- `0x180011420`
- `0x1800114a0`
- `0x180011540`
- `0x1800115e0`

## callees

- `0x1800035a8`
- `0x180010578`
- `0x18001b3a8`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800106ac`
- `KERNEL32!CloseHandle` at `0x180010728`
- `KERNEL32!CloseHandle` at `0x1800106ac`
- `KERNEL32!CloseHandle` at `0x180010728`
- `KERNEL32!CreateThread` at `0x1800105ee`
- `KERNEL32!CreateThread` at `0x1800105ee`
- `KERNEL32!WaitForSingleObjectEx` at `0x180010615`
- `KERNEL32!WaitForSingleObjectEx` at `0x18001069f`
- `KERNEL32!WaitForSingleObjectEx` at `0x180010615`
- `KERNEL32!WaitForSingleObjectEx` at `0x18001069f`
- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x18001068a`
- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x18001068a`

## string_xrefs

- `0x180010646`: `Out-of-proc diagnostic function timed out after %i seconds, will CoCancel the COM call, and wait for thread to exit cleanly. [op:%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CallDiagFunctionWithCOMTimeout(struct tagDiagThreadContext *lpParameter)
{
  __int64 v3; // rsi
  HANDLE *v4; // rbx
  void *v5; // rcx
  HRESULT v6; // ebx
  unsigned int v7; // ebx
  DWORD ThreadId[4]; // [rsp+30h] [rbp-1C8h] BYREF
  unsigned __int16 v9[192]; // [rsp+40h] [rbp-1B8h] BYREF

  if ( **((_QWORD **)lpParameter + 1) )
    return 2147942421LL;
  v3 = 0;
  if ( NetworkDiagnosticsEngine::Instance() )
    v3 = *(_QWORD *)NetworkDiagnosticsEngine::Instance();
  v4 = (HANDLE *)*((_QWORD *)lpParameter + 1);
  ThreadId[0] = 0;
  *v4 = CreateThread(0, 0, DiagThread, lpParameter, 0, ThreadId);
  v5 = (void *)**((_QWORD **)lpParameter + 1);
  if ( !v5 )
    return 2147943454LL;
  if ( WaitForSingleObjectEx(v5, 0xAFC8u, 0) == 258 )
  {
    if ( v3 )
    {
      memset_0(v9, 0, sizeof(v9));
      StringCchPrintfW(
        v9,
        0xC0u,
        L"Out-of-proc diagnostic function timed out after %i seconds, will CoCancel the COM call, and wait for thread to e"
         "xit cleanly. [op:%s]",
        45,
        (&g_diagThreadActionStrings)[*((int *)lpParameter + 4)]);
      (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v3 + 96LL))(v3, 6, v9);
    }
    v6 = CoCancelCall(ThreadId[0], 0);
    WaitForSingleObjectEx(**((HANDLE **)lpParameter + 1), 0xFFFFFFFF, 0);
    CloseHandle(**((HANDLE **)lpParameter + 1));
    if ( v6 < 0 )
    {
      if ( v3 )
      {
        if ( v6 != -2147417833 )
        {
          memset_0(v9, 0, 0x100u);
          StringCchPrintfW(
            v9,
            0x80u,
            L"CoCancelCall call failed with HR=0x%x [op:%s]",
            (unsigned int)v6,
            (&g_diagThreadActionStrings)[*((int *)lpParameter + 4)]);
          (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v3 + 96LL))(v3, 6, v9);
        }
      }
      return *(unsigned int *)lpParameter;
    }
    else
    {
      return (unsigned int)-2147023436;
    }
  }
  else
  {
    v7 = *(_DWORD *)lpParameter;
    CloseHandle(**((HANDLE **)lpParameter + 1));
    **((_QWORD **)lpParameter + 1) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180010578  push    rbx
0x18001057a  push    rsi
0x18001057b  push    rdi
0x18001057c  push    r15
0x18001057e  sub     rsp, 1D8h
0x180010585  mov     rax, cs:__security_cookie
0x18001058c  xor     rax, rsp
0x18001058f  mov     [rsp+1F8h+var_38], rax
0x180010597  mov     rax, [rcx+8]
0x18001059b  mov     rdi, rcx
0x18001059e  cmp     qword ptr [rax], 0
0x1800105a2  jz      short loc_1800105AE
0x1800105a4  mov     eax, 80070015h
0x1800105a9  jmp     loc_18001073B
0x1800105ae  xor     esi, esi
0x1800105b0  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x1800105b5  test    rax, rax
0x1800105b8  jz      short loc_1800105C2
0x1800105ba  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x1800105bf  mov     rsi, [rax]
0x1800105c2  mov     rbx, [rdi+8]
0x1800105c6  lea     rax, [rsp+1F8h+ThreadId]
0x1800105cb  mov     [rsp+1F8h+lpThreadId], rax; lpThreadId
0x1800105d0  lea     r8, ?DiagThread@@YAKPEAX@Z; lpStartAddress
0x1800105d7  mov     r9, rdi; lpParameter
0x1800105da  mov     [rsp+1F8h+dwCreationFlags], 0; dwCreationFlags
0x1800105e2  xor     edx, edx; dwStackSize
0x1800105e4  mov     [rsp+1F8h+ThreadId], 0
0x1800105ec  xor     ecx, ecx; lpThreadAttributes
0x1800105ee  call    cs:__imp_CreateThread
0x1800105f4  mov     [rbx], rax
0x1800105f7  mov     rax, [rdi+8]
0x1800105fb  mov     rcx, [rax]; hHandle
0x1800105fe  test    rcx, rcx
0x180010601  jnz     short loc_18001060D
0x180010603  mov     eax, 8007041Eh
0x180010608  jmp     loc_18001073B
0x18001060d  xor     r8d, r8d; bAlertable
0x180010610  mov     edx, 0AFC8h; dwMilliseconds
0x180010615  call    cs:__imp_WaitForSingleObjectEx
0x18001061b  cmp     eax, 102h
0x180010620  jnz     loc_18001071F
0x180010626  lea     r15, ?g_diagThreadActionStrings@@3PAPEAGA; ushort * near * g_diagThreadActionStrings
0x18001062d  test    rsi, rsi
0x180010630  jz      short loc_180010684
0x180010632  xor     edx, edx; Val
0x180010634  lea     r8d, [rax+7Eh]; Size
0x180010638  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x18001063d  call    memset_0
0x180010642  movsxd  rax, dword ptr [rdi+10h]
0x180010646  lea     r8, aOutOfProcDiagn; "Out-of-proc diagnostic function timed o"...
0x18001064d  mov     r9d, 2Dh ; '-'
0x180010653  lea     rcx, [rsp+1F8h+var_1B8]; unsigned __int16 *
0x180010658  mov     edx, 0C0h; unsigned __int64
0x18001065d  mov     rax, [r15+rax*8]
0x180010661  mov     qword ptr [rsp+1F8h+dwCreationFlags], rax
0x180010666  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001066b  mov     rax, [rsi]
0x18001066e  lea     r8, [rsp+1F8h+var_1B8]
0x180010673  mov     edx, 6
0x180010678  mov     rcx, rsi
0x18001067b  mov     rax, [rax+60h]
0x18001067f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010684  mov     ecx, [rsp+1F8h+ThreadId]; dwThreadId
0x180010688  xor     edx, edx; ulTimeout
0x18001068a  call    cs:__imp_CoCancelCall
0x180010690  mov     rcx, [rdi+8]
0x180010694  xor     r8d, r8d; bAlertable
0x180010697  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001069a  mov     ebx, eax
0x18001069c  mov     rcx, [rcx]; hHandle
0x18001069f  call    cs:__imp_WaitForSingleObjectEx
0x1800106a5  mov     rcx, [rdi+8]
0x1800106a9  mov     rcx, [rcx]; hObject
0x1800106ac  call    cs:__imp_CloseHandle
0x1800106b2  test    ebx, ebx
0x1800106b4  js      short loc_1800106BD
0x1800106b6  mov     ebx, 800705B4h
0x1800106bb  jmp     short loc_180010739
0x1800106bd  test    rsi, rsi
0x1800106c0  jz      short loc_18001071B
0x1800106c2  cmp     ebx, 80010117h
0x1800106c8  jz      short loc_18001071B
0x1800106ca  xor     edx, edx; Val
0x1800106cc  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1800106d1  mov     r8d, 100h; Size
0x1800106d7  call    memset_0
0x1800106dc  movsxd  rax, dword ptr [rdi+10h]
0x1800106e0  lea     r8, aCocancelcallCa; "CoCancelCall call failed with HR=0x%x ["...
0x1800106e7  mov     r9d, ebx
0x1800106ea  lea     rcx, [rsp+1F8h+var_1B8]; unsigned __int16 *
0x1800106ef  mov     edx, 80h; unsigned __int64
0x1800106f4  mov     rax, [r15+rax*8]
0x1800106f8  mov     qword ptr [rsp+1F8h+dwCreationFlags], rax
0x1800106fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010702  mov     rax, [rsi]
0x180010705  lea     r8, [rsp+1F8h+var_1B8]
0x18001070a  mov     edx, 6
0x18001070f  mov     rcx, rsi
0x180010712  mov     rax, [rax+60h]
0x180010716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001071b  mov     ebx, [rdi]
0x18001071d  jmp     short loc_180010739
0x18001071f  mov     rcx, [rdi+8]
0x180010723  mov     ebx, [rdi]
0x180010725  mov     rcx, [rcx]; hObject
0x180010728  call    cs:__imp_CloseHandle
0x18001072e  mov     rcx, [rdi+8]
0x180010732  mov     qword ptr [rcx], 0
0x180010739  mov     eax, ebx
0x18001073b  mov     rcx, [rsp+1F8h+var_38]
0x180010743  xor     rcx, rsp; StackCookie
0x180010746  call    __security_check_cookie
0x18001074b  add     rsp, 1D8h
0x180010752  pop     r15
0x180010754  pop     rdi
0x180010755  pop     rsi
0x180010756  pop     rbx
0x180010757  retn
```
