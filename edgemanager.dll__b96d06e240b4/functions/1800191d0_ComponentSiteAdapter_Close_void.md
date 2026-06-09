# ComponentSiteAdapter::Close(void)

- ea: `0x1800191d0`
- end: `0x1800192a0`
- name: `?Close@ComponentSiteAdapter@@UEAAJXZ`
- size: `208`
- prototype: `__int64 __fastcall(ComponentSiteAdapter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800191d0`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x180019212`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x180019223`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x180019212`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x180019223`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800191e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800191e7`

## string_xrefs

- `0x180019245`: `onecoreuap\inetcore\edgemanager\webview\corewebview\componentsiteadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ComponentSiteAdapter::Close(ComponentSiteAdapter *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  HWND v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 176);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  *((_BYTE *)this + 229) = 1;
  if ( v2 )
    LeaveCriticalSection(v2);
  v3 = (HWND)*((_QWORD *)this + 8);
  if ( v3 )
  {
    RemovePropW(v3, L"UIA_HWNDWidth");
    RemovePropW(*((HWND *)this + 8), L"UIA_HWNDHeight");
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 64LL))(*((_QWORD *)this + 10));
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\componentsiteadapter.cpp",
      (const char *)(unsigned int)v4,
      v8);
  v5 = *((_QWORD *)this + 10);
  if ( v5 )
  {
    *((_QWORD *)this + 10) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)this + 13);
  if ( v6 )
  {
    *((_QWORD *)this + 13) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800191d0  mov     [rsp+arg_0], rbx
0x1800191d5  push    rdi; int
0x1800191d6  sub     rsp, 20h
0x1800191da  mov     rbx, rcx
0x1800191dd  lea     rdi, [rcx+0B0h]
0x1800191e4  mov     rcx, rdi; lpCriticalSection
0x1800191e7  call    cs:__imp_EnterCriticalSection
0x1800191ed  mov     byte ptr [rbx+0E5h], 1
0x1800191f4  test    rdi, rdi
0x1800191f7  jz      short loc_180019202
0x1800191f9  mov     rcx, rdi; lpCriticalSection
0x1800191fc  call    cs:__imp_LeaveCriticalSection
0x180019202  mov     rcx, [rbx+40h]; hWnd
0x180019206  test    rcx, rcx
0x180019209  jz      short loc_180019229
0x18001920b  lea     rdx, aUiaHwndwidth; "UIA_HWNDWidth"
0x180019212  call    cs:__imp_RemovePropW
0x180019218  lea     rdx, aUiaHwndheight; "UIA_HWNDHeight"
0x18001921f  mov     rcx, [rbx+40h]; hWnd
0x180019223  call    cs:__imp_RemovePropW
0x180019229  mov     rcx, [rbx+50h]
0x18001922d  mov     rax, [rcx]
0x180019230  mov     rax, [rax+40h]
0x180019234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019239  mov     rcx, [rsp+28h]; this
0x18001923e  test    eax, eax
0x180019240  jns     short loc_180019257
0x180019242  mov     r9d, eax; char *
0x180019245  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001924c  mov     edx, 0FEh; void *
0x180019251  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180019257  mov     rcx, [rbx+50h]
0x18001925b  test    rcx, rcx
0x18001925e  jz      short loc_180019275
0x180019260  mov     qword ptr [rbx+50h], 0
0x180019268  mov     rax, [rcx]
0x18001926b  mov     rax, [rax+10h]
0x18001926f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019274  nop
0x180019275  mov     rcx, [rbx+68h]
0x180019279  test    rcx, rcx
0x18001927c  jz      short loc_180019293
0x18001927e  mov     qword ptr [rbx+68h], 0
0x180019286  mov     rax, [rcx]
0x180019289  mov     rax, [rax+10h]
0x18001928d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019292  nop
0x180019293  xor     eax, eax
0x180019295  mov     rbx, [rsp+28h+arg_0]
0x18001929a  add     rsp, 20h
0x18001929e  pop     rdi
0x18001929f  retn
```
