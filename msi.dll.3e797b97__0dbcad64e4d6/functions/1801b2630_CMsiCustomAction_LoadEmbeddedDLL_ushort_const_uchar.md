# CMsiCustomAction::LoadEmbeddedDLL(ushort const *,uchar)

- ea: `0x1801b2630`
- end: `0x1801b2936`
- name: `?LoadEmbeddedDLL@CMsiCustomAction@@UEAAJPEBGE@Z`
- size: `774`
- prototype: `int(CMsiCustomAction *__hidden this, const unsigned __int16 *, unsigned __int8)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c4bc`
- `0x180010ac0`
- `0x18009436c`
- `0x1800d08d0`
- `0x1801b2630`
- `0x1801b56d0`
- `0x180259808`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1801b270b`
- `KERNEL32!LeaveCriticalSection` at `0x1801b2866`
- `KERNEL32!LeaveCriticalSection` at `0x1801b28fb`
- `KERNEL32!LeaveCriticalSection` at `0x1801b270b`
- `KERNEL32!LeaveCriticalSection` at `0x1801b2866`
- `KERNEL32!LeaveCriticalSection` at `0x1801b28fb`
- `KERNEL32!IsDebuggerPresent` at `0x1801b2788`
- `KERNEL32!IsDebuggerPresent` at `0x1801b2788`
- `KERNEL32!GetProcAddress` at `0x1801b2732`
- `KERNEL32!GetProcAddress` at `0x1801b274f`
- `KERNEL32!GetProcAddress` at `0x1801b276c`
- `KERNEL32!GetProcAddress` at `0x1801b2732`
- `KERNEL32!GetProcAddress` at `0x1801b274f`
- `KERNEL32!GetProcAddress` at `0x1801b276c`
- `KERNEL32!EnterCriticalSection` at `0x1801b2675`
- `KERNEL32!EnterCriticalSection` at `0x1801b2675`
- `KERNEL32!GetCurrentProcessId` at `0x1801b27b9`
- `KERNEL32!GetCurrentProcessId` at `0x1801b27c7`
- `KERNEL32!GetCurrentProcessId` at `0x1801b27b9`
- `KERNEL32!GetCurrentProcessId` at `0x1801b27c7`
- `KERNEL32!SetErrorMode` at `0x1801b26d1`
- `KERNEL32!SetErrorMode` at `0x1801b26f7`
- `KERNEL32!SetErrorMode` at `0x1801b28e3`
- `KERNEL32!SetErrorMode` at `0x1801b26d1`
- `KERNEL32!SetErrorMode` at `0x1801b26f7`
- `KERNEL32!SetErrorMode` at `0x1801b28e3`
- `USER32!MessageBoxW` at `0x1801b2857`
- `USER32!MessageBoxW` at `0x1801b2857`

## string_xrefs

- `0x1801b26ba`: `EEUI - Custom action server trying to load this DLL: %s`
- `0x1801b28cd`: `EEUI - Custom action server threw an exception during load: (%u), returning %u`

## pseudocode

```c
__int64 __fastcall CMsiCustomAction::LoadEmbeddedDLL(CMsiCustomAction *this, const unsigned __int16 *a2, char a3)
{
  UINT v6; // r14d
  HMODULE LibraryW; // rbx
  DWORD CurrentProcessId; // ebx
  DWORD v10; // eax
  unsigned __int16 *v11; // [rsp+20h] [rbp-308h]
  WCHAR Caption; // [rsp+80h] [rbp-2A8h] BYREF
  _BYTE v13[126]; // [rsp+82h] [rbp-2A6h] BYREF
  WCHAR Text; // [rsp+100h] [rbp-228h] BYREF
  _BYTE v15[510]; // [rsp+102h] [rbp-226h] BYREF

  CMsiCustomAction::WaitForCAMainThread(this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 792));
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"EEUI - Custom action server trying to load this DLL: %s",
      a2,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  v6 = SetErrorMode(1u);
  LibraryW = (HMODULE)IsolationAwareLoadLibraryW(a2);
  SetErrorMode(v6);
  if ( LibraryW )
  {
    *((_QWORD *)this + 98) = LibraryW;
    *((_QWORD *)this + 95) = GetProcAddress(LibraryW, "InitializeEmbeddedUI");
    *((_QWORD *)this + 96) = GetProcAddress(LibraryW, "ShutdownEmbeddedUI");
    *((_QWORD *)this + 97) = GetProcAddress(LibraryW, "EmbeddedUIHandler");
    if ( a3 )
    {
      if ( !IsDebuggerPresent() )
      {
        Text = 0;
        memset_0(v15, 0, sizeof(v15));
        CurrentProcessId = GetCurrentProcessId();
        v10 = GetCurrentProcessId();
        LODWORD(v11) = CurrentProcessId;
        if ( (int)StringCchPrintfW(
                    &Text,
                    0x100u,
                    L"To debug Embedded UI, attach your debugger to process %d (0x%X) and press OK",
                    v10,
                    v11) >= 0 )
        {
          Caption = 0;
          memset_0(v13, 0, sizeof(v13));
          if ( !(unsigned int)MsiLoadStringW((HMODULE)0xFFFFFFFFFFFFFFFFLL, 0) )
            Caption = 0;
          MessageBoxW(0, &Text, &Caption, 0x200000u);
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 792));
    return 0;
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 792));
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1801b2630  mov     [rsp+arg_10], rbx
0x1801b2635  mov     [rsp+arg_18], rsi
0x1801b263a  push    rdi
0x1801b263b  push    r14
0x1801b263d  push    r15
0x1801b263f  sub     rsp, 310h
0x1801b2646  mov     rax, cs:__security_cookie
0x1801b264d  xor     rax, rsp
0x1801b2650  mov     [rsp+328h+var_28], rax
0x1801b2658  mov     r15b, r8b
0x1801b265b  mov     rbx, rdx
0x1801b265e  mov     rdi, rcx
0x1801b2661  mov     [rsp+328h+var_2C0], rcx
0x1801b2666  call    ?WaitForCAMainThread@CMsiCustomAction@@AEAAXXZ; CMsiCustomAction::WaitForCAMainThread(void)
0x1801b266b  lea     rsi, [rdi+318h]
0x1801b2672  mov     rcx, rsi; lpCriticalSection
0x1801b2675  call    cs:__imp_EnterCriticalSection
0x1801b267c  nop     dword ptr [rax+rax+00h]
0x1801b2681  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801b2688  jz      short loc_1801B26CC
0x1801b268a  xor     edx, edx; unsigned __int16
0x1801b268c  mov     [rsp+328h+var_2D0], rdx; void *
0x1801b2691  mov     [rsp+328h+var_2D8], edx; unsigned int
0x1801b2695  lea     rax, aNull; "(NULL)"
0x1801b269c  mov     [rsp+328h+var_2E0], rax; unsigned __int16 *
0x1801b26a1  mov     [rsp+328h+var_2E8], rax; unsigned __int16 *
0x1801b26a6  mov     [rsp+328h+var_2F0], rax; unsigned __int16 *
0x1801b26ab  mov     [rsp+328h+var_2F8], rax; unsigned __int16 *
0x1801b26b0  mov     [rsp+328h+var_300], rax; unsigned __int16 *
0x1801b26b5  mov     [rsp+328h+var_308], rbx; unsigned __int16 *
0x1801b26ba  lea     r9, aEeuiCustomActi_0; "EEUI - Custom action server trying to l"...
0x1801b26c1  xor     r8d, r8d; int
0x1801b26c4  lea     ecx, [rdx+9]; int
0x1801b26c7  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801b26cc  mov     ecx, 1; uMode
0x1801b26d1  call    cs:__imp_SetErrorMode
0x1801b26d8  nop     dword ptr [rax+rax+00h]
0x1801b26dd  mov     r14d, eax
0x1801b26e0  mov     [rsp+328h+uMode], eax
0x1801b26e4  mov     rcx, rbx; lpLibFileName
0x1801b26e7  call    IsolationAwareLoadLibraryW
0x1801b26ec  mov     rbx, rax
0x1801b26ef  mov     [rsp+328h+var_2B8], rax
0x1801b26f4  mov     ecx, r14d; uMode
0x1801b26f7  call    cs:__imp_SetErrorMode
0x1801b26fe  nop     dword ptr [rax+rax+00h]
0x1801b2703  test    rbx, rbx
0x1801b2706  jnz     short loc_1801B2721
0x1801b2708  mov     rcx, rsi; lpCriticalSection
0x1801b270b  call    cs:__imp_LeaveCriticalSection
0x1801b2712  nop     dword ptr [rax+rax+00h]
0x1801b2717  mov     eax, 80004005h
0x1801b271c  jmp     loc_1801B290C
0x1801b2721  mov     [rdi+310h], rbx
0x1801b2728  lea     rdx, aInitializeembe; "InitializeEmbeddedUI"
0x1801b272f  mov     rcx, rbx; hModule
0x1801b2732  call    cs:__imp_GetProcAddress
0x1801b2739  nop     dword ptr [rax+rax+00h]
0x1801b273e  mov     [rdi+2F8h], rax
0x1801b2745  lea     rdx, aShutdownembedd; "ShutdownEmbeddedUI"
0x1801b274c  mov     rcx, rbx; hModule
0x1801b274f  call    cs:__imp_GetProcAddress
0x1801b2756  nop     dword ptr [rax+rax+00h]
0x1801b275b  mov     [rdi+300h], rax
0x1801b2762  lea     rdx, aEmbeddeduihand; "EmbeddedUIHandler"
0x1801b2769  mov     rcx, rbx; hModule
0x1801b276c  call    cs:__imp_GetProcAddress
0x1801b2773  nop     dword ptr [rax+rax+00h]
0x1801b2778  mov     [rdi+308h], rax
0x1801b277f  test    r15b, r15b
0x1801b2782  jz      loc_1801B2863
0x1801b2788  call    cs:__imp_IsDebuggerPresent
0x1801b278f  nop     dword ptr [rax+rax+00h]
0x1801b2794  test    eax, eax
0x1801b2796  jnz     loc_1801B2863
0x1801b279c  mov     [rsp+328h+Text], ax
0x1801b27a4  xor     edx, edx; Val
0x1801b27a6  mov     r8d, 1FEh; Size
0x1801b27ac  lea     rcx, [rsp+328h+var_226]; void *
0x1801b27b4  call    memset_0
0x1801b27b9  call    cs:__imp_GetCurrentProcessId
0x1801b27c0  nop     dword ptr [rax+rax+00h]
0x1801b27c5  mov     ebx, eax
0x1801b27c7  call    cs:__imp_GetCurrentProcessId
0x1801b27ce  nop     dword ptr [rax+rax+00h]
0x1801b27d3  mov     dword ptr [rsp+328h+var_308], ebx
0x1801b27d7  mov     r9d, eax
0x1801b27da  lea     r8, aToDebugEmbedde; "To debug Embedded UI, attach your debug"...
0x1801b27e1  mov     edx, 100h; unsigned __int64
0x1801b27e6  lea     rcx, [rsp+328h+Text]; unsigned __int16 *
0x1801b27ee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801b27f3  test    eax, eax
0x1801b27f5  js      short loc_1801B2863
0x1801b27f7  xor     eax, eax
0x1801b27f9  mov     [rsp+328h+Caption], ax
0x1801b2801  xor     edx, edx; Val
0x1801b2803  lea     r8d, [rax+7Eh]; Size
0x1801b2807  lea     rcx, [rsp+328h+var_2A6]; void *
0x1801b280f  call    memset_0
0x1801b2814  xor     eax, eax
0x1801b2816  mov     word ptr [rsp+328h+var_308], ax; unsigned __int16
0x1801b281b  lea     r9d, [rax+40h]
0x1801b281f  lea     r8, [rsp+328h+Caption]
0x1801b2827  lea     edx, [rax+1Ch]
0x1801b282a  or      rcx, 0FFFFFFFFFFFFFFFFh; hModule
0x1801b282e  call    MsiLoadStringW
0x1801b2833  test    eax, eax
0x1801b2835  jnz     short loc_1801B283F
0x1801b2837  mov     [rsp+328h+Caption], ax
0x1801b283f  mov     r9d, 200000h; uType
0x1801b2845  lea     r8, [rsp+328h+Caption]; lpCaption
0x1801b284d  lea     rdx, [rsp+328h+Text]; lpText
0x1801b2855  xor     ecx, ecx; hWnd
0x1801b2857  call    cs:__imp_MessageBoxW
0x1801b285e  nop     dword ptr [rax+rax+00h]
0x1801b2863  mov     rcx, rsi; lpCriticalSection
0x1801b2866  call    cs:__imp_LeaveCriticalSection
0x1801b286d  nop     dword ptr [rax+rax+00h]
0x1801b2872  xor     eax, eax
0x1801b2874  jmp     loc_1801B290C
0x1801b2879  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1801b2880  jz      short loc_1801B28DF
0x1801b2882  mov     eax, eax
0x1801b2884  xor     edx, edx; unsigned __int16
0x1801b2886  mov     [rsp+328h+var_2D0], rdx; void *
0x1801b288b  mov     [rsp+328h+var_2D8], edx; unsigned int
0x1801b288f  lea     rcx, aNull; "(NULL)"
0x1801b2896  mov     [rsp+328h+var_2E0], rcx; unsigned __int16 *
0x1801b289b  lea     rcx, aNull; "(NULL)"
0x1801b28a2  mov     [rsp+328h+var_2E8], rcx; unsigned __int16 *
0x1801b28a7  lea     rcx, aNull; "(NULL)"
0x1801b28ae  mov     [rsp+328h+var_2F0], rcx; unsigned __int16 *
0x1801b28b3  lea     rcx, aNull; "(NULL)"
0x1801b28ba  mov     [rsp+328h+var_2F8], rcx; unsigned __int16 *
0x1801b28bf  mov     [rsp+328h+var_300], 643h; unsigned __int16 *
0x1801b28c8  mov     [rsp+328h+var_308], rax; unsigned __int16 *
0x1801b28cd  lea     r9, aEeuiCustomActi_1; "EEUI - Custom action server threw an ex"...
0x1801b28d4  xor     r8d, r8d; int
0x1801b28d7  lea     ecx, [rdx+9]; int
0x1801b28da  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801b28df  mov     ecx, [rsp+328h+uMode]; uMode
0x1801b28e3  call    cs:__imp_SetErrorMode
0x1801b28ea  nop     dword ptr [rax+rax+00h]
0x1801b28ef  mov     rcx, [rsp+328h+var_2C0]
0x1801b28f4  add     rcx, 318h; lpCriticalSection
0x1801b28fb  call    cs:__imp_LeaveCriticalSection
0x1801b2902  nop     dword ptr [rax+rax+00h]
0x1801b2907  mov     eax, 80004005h
0x1801b290c  mov     rcx, [rsp+328h+var_28]
0x1801b2914  xor     rcx, rsp; StackCookie
0x1801b2917  call    __security_check_cookie
0x1801b291c  lea     r11, [rsp+328h+var_18]
0x1801b2924  mov     rbx, [r11+30h]
0x1801b2928  mov     rsi, [r11+38h]
0x1801b292c  mov     rsp, r11
0x1801b292f  pop     r15
0x1801b2931  pop     r14
0x1801b2933  pop     rdi
0x1801b2934  retn
0x180265876  push    rbp
0x180265878  sub     rsp, 60h
0x18026587c  mov     rbp, rdx
0x18026587f  call    ?CustomActionExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; CustomActionExceptionFilter(_EXCEPTION_POINTERS *)
0x180265884  nop
0x180265885  add     rsp, 60h
0x180265889  pop     rbp
0x18026588a  retn
```
