# WebRuntimeDiagnostics::DiagnosticsTargetData::DiagnosticsTargetData(WebRuntime::Diagnostics::DiagnosticsTargetType,HSTRING__ * const)

- ea: `0x180011f08`
- end: `0x180011fd2`
- name: `??0DiagnosticsTargetData@WebRuntimeDiagnostics@@QEAA@W4DiagnosticsTargetType@Diagnostics@WebRuntime@@QEAUHSTRING__@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011cc8`
- `0x18006b5d0`

## callees

- `0x180011910`
- `0x180011af4`
- `0x180011f08`
- `0x180035b88`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180011fbe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180011fbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011f84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011f84`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WebRuntimeDiagnostics::DiagnosticsTargetData::DiagnosticsTargetData(
        __int64 a1,
        UINT32 a2,
        HSTRING a3)
{
  HSTRING *v4; // rbx
  GuidHelper *StringRawBuffer; // rax
  struct _GUID *v6; // r9
  int v7; // eax
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  UINT32 length; // [rsp+48h] [rbp+10h] BYREF
  HSTRING v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = a3;
  length = a2;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 16) = 0;
  *(GUID *)(a1 + 20) = GUID_NULL;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  v4 = (HSTRING *)(a1 + 64);
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 72) = 0;
  Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 64), &v12);
  length = 0;
  StringRawBuffer = (GuidHelper *)WindowsGetStringRawBuffer(*v4, &length);
  v7 = GuidHelper::ConvertStringToGuid(StringRawBuffer, (const unsigned __int16 *)length, (GUID *)(a1 + 20), v6);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstargetdata.cpp",
      (const char *)(unsigned int)v7,
      v9);
  *(_DWORD *)(a1 + 16) = GetWindowThreadProcessId(*(HWND *)(a1 + 8), 0);
  return a1;
}

```

## disassembly

```asm
0x180011f08  mov     rax, rsp
0x180011f0b  mov     [rax+18h], r8
0x180011f0f  mov     [rax+10h], edx
0x180011f12  mov     [rax+8], rcx
0x180011f16  push    rbx
0x180011f17  push    rsi
0x180011f18  push    rdi; int
0x180011f19  sub     rsp, 20h
0x180011f1d  mov     rsi, rcx
0x180011f20  mov     qword ptr [rcx], 0
0x180011f27  mov     qword ptr [rcx+8], 0
0x180011f2f  mov     dword ptr [rcx+10h], 0
0x180011f36  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180011f3d  movdqu  xmmword ptr [rcx+14h], xmm0
0x180011f42  mov     qword ptr [rcx+28h], 0
0x180011f4a  mov     qword ptr [rcx+30h], 0
0x180011f52  mov     byte ptr [rcx+38h], 0
0x180011f56  lea     rbx, [rcx+40h]
0x180011f5a  mov     qword ptr [rbx], 0
0x180011f61  mov     dword ptr [rcx+48h], 0
0x180011f68  lea     rdx, [rax+18h]; HSTRING *
0x180011f6c  mov     rcx, rbx; newString
0x180011f6f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180011f74  mov     [rsp+38h+length], 0
0x180011f7c  lea     rdx, [rsp+38h+length]; length
0x180011f81  mov     rcx, [rbx]; string
0x180011f84  call    cs:__imp_WindowsGetStringRawBuffer
0x180011f8a  mov     edx, [rsp+38h+length]; unsigned __int16 *
0x180011f8e  lea     r8, [rsi+14h]; unsigned __int64
0x180011f92  mov     rcx, rax; this
0x180011f95  call    ?ConvertStringToGuid@GuidHelper@@YAJPEBG_KPEAU_GUID@@@Z; GuidHelper::ConvertStringToGuid(ushort const *,unsigned __int64,_GUID *)
0x180011f9a  mov     rcx, [rsp+38h]; this
0x180011f9f  test    eax, eax
0x180011fa1  jns     short loc_180011FB8
0x180011fa3  mov     r9d, eax; char *
0x180011fa6  lea     r8, aOnecoreuapInet_45; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180011fad  mov     edx, 87h; void *
0x180011fb2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180011fb8  xor     edx, edx; lpdwProcessId
0x180011fba  mov     rcx, [rsi+8]; hWnd
0x180011fbe  call    cs:__imp_GetWindowThreadProcessId
0x180011fc4  mov     [rsi+10h], eax
0x180011fc7  mov     rax, rsi
0x180011fca  add     rsp, 20h
0x180011fce  pop     rdi
0x180011fcf  pop     rsi
0x180011fd0  pop     rbx
0x180011fd1  retn
```
