# MFD3D12Sync::OpenSharedHandleToReadyFence(void * *)

- ea: `0x18006a9b0`
- end: `0x18006aa58`
- name: `?OpenSharedHandleToReadyFence@MFD3D12Sync@@UEAAJPEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002312c`
- `0x180054b90`
- `0x180056638`
- `0x18006a9b0`
- `0x180070010`

## string_xrefs

- `0x18006a9f9`: `MFD3D12Sync::OpenSharedHandleToReadyFence`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::OpenSharedHandleToReadyFence(MFD3D12Sync *this, void **a2)
{
  char *v3; // rsi
  unsigned int v4; // ebx
  char v6; // [rsp+50h] [rbp+8h] BYREF

  v3 = (char *)this - 16;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD, void **))(**((_QWORD **)this + 13) + 248LL))(
         *((_QWORD *)this + 13),
         *((_QWORD *)this + 14),
         0,
         0x10000000,
         0,
         a2);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v6, "MFD3D12Sync::OpenSharedHandleToReadyFence", 156);
  if ( g_wppLevels >= 0x10u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids, v3, *a2);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v6);
  return v4;
}

```

## disassembly

```asm
0x18006a9b0  mov     r11, rsp
0x18006a9b3  mov     [r11+10h], rbx
0x18006a9b7  mov     [r11+18h], rsi
0x18006a9bb  push    rdi
0x18006a9bc  sub     rsp, 40h
0x18006a9c0  mov     rdi, rdx
0x18006a9c3  lea     rsi, [rcx-10h]
0x18006a9c7  mov     rdx, [rcx+70h]
0x18006a9cb  mov     r9d, 10000000h
0x18006a9d1  mov     rcx, [rsi+78h]
0x18006a9d5  xor     r8d, r8d
0x18006a9d8  mov     [r11-20h], rdi
0x18006a9dc  mov     qword ptr [r11-28h], 0
0x18006a9e4  mov     rax, [rcx]
0x18006a9e7  mov     rax, [rax+0F8h]
0x18006a9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a9f3  mov     r8d, 9Ch; int
0x18006a9f9  lea     rdx, aMfd3d12syncOpe_0; "MFD3D12Sync::OpenSharedHandleToReadyFen"...
0x18006aa00  lea     rcx, [rsp+48h+arg_0]; this
0x18006aa05  mov     ebx, eax
0x18006aa07  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006aa0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x18006aa13  jb      short loc_18006AA3C
0x18006aa15  mov     rcx, [rdi]
0x18006aa18  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x18006aa1f  mov     [rsp+48h+var_28], rcx
0x18006aa24  mov     edx, 24h ; '$'
0x18006aa29  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aa30  mov     r9, rsi
0x18006aa33  mov     rcx, [rcx+10h]
0x18006aa37  call    WPP_SF_qq
0x18006aa3c  lea     rcx, [rsp+48h+arg_0]; this
0x18006aa41  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006aa46  mov     rsi, [rsp+48h+arg_10]
0x18006aa4b  mov     eax, ebx
0x18006aa4d  mov     rbx, [rsp+48h+arg_8]
0x18006aa52  add     rsp, 40h
0x18006aa56  pop     rdi
0x18006aa57  retn
```
