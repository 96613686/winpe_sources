# DllMain

- ea: `0x1800116dc`
- end: `0x180011887`
- name: `DllMain`
- size: `427`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000b634`

## callees

- `0x1800085b0`
- `0x1800116dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011713`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011713`
- `ntdll!EtwUnregisterTraceGuids` at `0x180011859`
- `ntdll!EtwUnregisterTraceGuids` at `0x180011859`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  _QWORD *v3; // rbx

  if ( fdwReason == 1 )
  {
    hProxyDll = hinstDLL;
    g_hInstance = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    qword_180046380 = 0;
    WPP_MAIN_CB = (__int64)&qword_180046398;
    qword_180046398 = (__int64)&qword_1800463C0;
    qword_1800463C0 = (__int64)&qword_1800463E8;
    qword_1800463E8 = (__int64)&qword_180046410;
    qword_180046410 = (__int64)&qword_180046438;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CscService;
    qword_180046468 = (__int64)WPP_ThisDir_CTLGUID_CscDclUser;
    qword_180046470 = (__int64)WPP_ThisDir_CTLGUID_CscFastSync;
    qword_180046478 = (__int64)WPP_ThisDir_CTLGUID_CscUm;
    qword_180046480 = (__int64)WPP_ThisDir_CTLGUID_CscApi;
    qword_180046488 = (__int64)WPP_ThisDir_CTLGUID_CscNetApi;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    qword_180046388 = 1;
    qword_1800463A8 = 0;
    qword_1800463B0 = 1;
    qword_1800463D0 = 0;
    qword_1800463D8 = 1;
    qword_1800463F8 = 0;
    qword_180046400 = 1;
    qword_180046420 = 0;
    qword_180046428 = 1;
    qword_180046448 = 0;
    qword_180046438 = 0;
    qword_180046450 = 1;
    WppInitUm();
  }
  else if ( !fdwReason )
  {
    v3 = (_QWORD *)WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v3 )
      {
        if ( v3[1] )
        {
          EtwUnregisterTraceGuids();
          v3[1] = 0;
        }
        v3 = (_QWORD *)*v3;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800116dc  mov     [rsp+arg_0], rbx
0x1800116e1  mov     [rsp+arg_8], rsi
0x1800116e6  push    rdi
0x1800116e7  sub     rsp, 20h
0x1800116eb  xor     edi, edi
0x1800116ed  cmp     edx, 1
0x1800116f0  jnz     short loc_1800116FB
0x1800116f2  mov     cs:hProxyDll, rcx
0x1800116f9  jmp     short loc_18001170C
0x1800116fb  test    edx, edx
0x1800116fd  jz      loc_18001183B
0x180011703  cmp     edx, 1
0x180011706  jnz     loc_180011872
0x18001170c  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x180011713  call    cs:__imp_DisableThreadLibraryCalls
0x180011719  lea     rax, qword_180046398
0x180011720  mov     cs:qword_180046380, rdi
0x180011727  mov     cs:WPP_MAIN_CB, rax
0x18001172e  lea     rax, qword_1800463C0
0x180011735  mov     cs:qword_180046398, rax
0x18001173c  lea     rax, qword_1800463E8
0x180011743  mov     cs:qword_1800463C0, rax
0x18001174a  lea     rax, qword_180046410
0x180011751  mov     cs:qword_1800463E8, rax
0x180011758  lea     rax, qword_180046438
0x18001175f  mov     cs:qword_180046410, rax
0x180011766  lea     rax, WPP_ThisDir_CTLGUID_CscService
0x18001176d  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180011774  lea     rax, WPP_ThisDir_CTLGUID_CscDclUser
0x18001177b  mov     cs:qword_180046468, rax
0x180011782  lea     rax, WPP_ThisDir_CTLGUID_CscFastSync
0x180011789  mov     cs:qword_180046470, rax
0x180011790  lea     rax, WPP_ThisDir_CTLGUID_CscUm
0x180011797  mov     cs:qword_180046478, rax
0x18001179e  lea     rax, WPP_ThisDir_CTLGUID_CscApi
0x1800117a5  mov     cs:qword_180046480, rax
0x1800117ac  lea     rax, WPP_ThisDir_CTLGUID_CscNetApi
0x1800117b3  mov     cs:qword_180046488, rax
0x1800117ba  lea     rax, WPP_MAIN_CB
0x1800117c1  mov     cs:WPP_GLOBAL_Control, rax
0x1800117c8  mov     cs:qword_180046388, 1
0x1800117d3  mov     cs:qword_1800463A8, rdi
0x1800117da  mov     cs:qword_1800463B0, 1
0x1800117e5  mov     cs:qword_1800463D0, rdi
0x1800117ec  mov     cs:qword_1800463D8, 1
0x1800117f7  mov     cs:qword_1800463F8, rdi
0x1800117fe  mov     cs:qword_180046400, 1
0x180011809  mov     cs:qword_180046420, rdi
0x180011810  mov     cs:qword_180046428, 1
0x18001181b  mov     cs:qword_180046448, rdi
0x180011822  mov     cs:qword_180046438, rdi
0x180011829  mov     cs:qword_180046450, 1
0x180011834  call    WppInitUm
0x180011839  jmp     short loc_180011872
0x18001183b  mov     rbx, cs:WPP_GLOBAL_Control
0x180011842  lea     rsi, WPP_GLOBAL_Control
0x180011849  cmp     rbx, rsi
0x18001184c  jz      short loc_180011872
0x18001184e  jmp     short loc_180011866
0x180011850  mov     rcx, [rbx+8]
0x180011854  test    rcx, rcx
0x180011857  jz      short loc_180011863
0x180011859  call    cs:__imp_EtwUnregisterTraceGuids
0x18001185f  mov     [rbx+8], rdi
0x180011863  mov     rbx, [rbx]
0x180011866  test    rbx, rbx
0x180011869  jnz     short loc_180011850
0x18001186b  mov     cs:WPP_GLOBAL_Control, rsi
0x180011872  mov     rbx, [rsp+28h+arg_0]
0x180011877  mov     eax, 1
0x18001187c  mov     rsi, [rsp+28h+arg_8]
0x180011881  add     rsp, 20h
0x180011885  pop     rdi
0x180011886  retn
```
