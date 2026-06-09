# EapHost::HostPeerApis::ConnectCallback(tagComCallData *)

- ea: `0x1800053d0`
- end: `0x18000548a`
- name: `?ConnectCallback@HostPeerApis@EapHost@@CAJPEAUtagComCallData@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002a90`
- `0x1800053d0`
- `0x180009d00`
- `0x180009dec`
- `0x18000f1e0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000541e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000541e`

## string_xrefs

- `0x180005432`: `ComOutOfProcRegisterClassObjects`

## pseudocode

```c
__int64 __fastcall EapHost::HostPeerApis::ConnectCallback(struct tagComCallData *a1)
{
  DWORD v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rcx
  WCHAR Buffer[1024]; // [rsp+40h] [rbp-818h] BYREF

  v1 = ComOutOfProcRegisterClassObjects();
  if ( (v1 & 0x80000000) != 0 )
  {
    FormatMessageW(0x1200u, 0, v1, 0, Buffer, 0x400u, 0);
    if ( (Microsoft_Windows_EapHostEnableBits & 0x10) != 0 )
      McTemplateU0sz_EtwEventWriteTransfer(v3, v2, "ComOutOfProcRegisterClassObjects", Buffer);
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids, v1);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800053d0  push    rbx
0x1800053d2  sub     rsp, 850h
0x1800053d9  mov     rax, cs:__security_cookie
0x1800053e0  xor     rax, rsp
0x1800053e3  mov     [rsp+858h+var_18], rax
0x1800053eb  call    ?ComOutOfProcRegisterClassObjects@@YAJXZ; ComOutOfProcRegisterClassObjects(void)
0x1800053f0  mov     ebx, eax
0x1800053f2  test    eax, eax
0x1800053f4  jns     short loc_18000546F
0x1800053f6  mov     [rsp+858h+Arguments], 0; Arguments
0x1800053ff  lea     rax, [rsp+858h+Buffer]
0x180005404  mov     [rsp+858h+nSize], 400h; nSize
0x18000540c  xor     r9d, r9d; dwLanguageId
0x18000540f  mov     r8d, ebx; dwMessageId
0x180005412  mov     [rsp+858h+lpBuffer], rax; lpBuffer
0x180005417  xor     edx, edx; lpSource
0x180005419  mov     ecx, 1200h; dwFlags
0x18000541e  call    cs:__imp_FormatMessageW
0x180005424  test    cs:Microsoft_Windows_EapHostEnableBits, 10h
0x18000542b  jz      short loc_18000543E
0x18000542d  lea     r9, [rsp+858h+Buffer]
0x180005432  lea     r8, aComoutofprocre; "ComOutOfProcRegisterClassObjects"
0x180005439  call    McTemplateU0sz_EtwEventWriteTransfer
0x18000543e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005445  lea     rax, WPP_GLOBAL_Control
0x18000544c  cmp     rcx, rax
0x18000544f  jz      short loc_18000546F
0x180005451  test    byte ptr [rcx+1Ch], 1
0x180005455  jz      short loc_18000546F
0x180005457  mov     rcx, [rcx+10h]
0x18000545b  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180005462  mov     edx, 16h
0x180005467  mov     r9d, ebx
0x18000546a  call    WPP_SF_d
0x18000546f  mov     eax, ebx
0x180005471  mov     rcx, [rsp+858h+var_18]
0x180005479  xor     rcx, rsp; StackCookie
0x18000547c  call    __security_check_cookie
0x180005481  add     rsp, 850h
0x180005488  pop     rbx
0x180005489  retn
```
