# EapHost::HostPeerApis::ConnectCallback(tagComCallData *)

- ea: `0x1800055d0`
- end: `0x180005691`
- name: `?ConnectCallback@HostPeerApis@EapHost@@CAJPEAUtagComCallData@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002af0`
- `0x1800055d0`
- `0x18000a154`
- `0x18000a24c`
- `0x18000f7e4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000561e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000561e`

## string_xrefs

- `0x180005638`: `ComOutOfProcRegisterClassObjects`

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
0x1800055d0  push    rbx
0x1800055d2  sub     rsp, 850h
0x1800055d9  mov     rax, cs:__security_cookie
0x1800055e0  xor     rax, rsp
0x1800055e3  mov     [rsp+858h+var_18], rax
0x1800055eb  call    ?ComOutOfProcRegisterClassObjects@@YAJXZ; ComOutOfProcRegisterClassObjects(void)
0x1800055f0  mov     ebx, eax
0x1800055f2  test    eax, eax
0x1800055f4  jns     short loc_180005675
0x1800055f6  mov     [rsp+858h+Arguments], 0; Arguments
0x1800055ff  lea     rax, [rsp+858h+Buffer]
0x180005604  mov     [rsp+858h+nSize], 400h; nSize
0x18000560c  xor     r9d, r9d; dwLanguageId
0x18000560f  mov     r8d, ebx; dwMessageId
0x180005612  mov     [rsp+858h+lpBuffer], rax; lpBuffer
0x180005617  xor     edx, edx; lpSource
0x180005619  mov     ecx, 1200h; dwFlags
0x18000561e  call    cs:__imp_FormatMessageW
0x180005625  nop     dword ptr [rax+rax+00h]
0x18000562a  test    cs:Microsoft_Windows_EapHostEnableBits, 10h
0x180005631  jz      short loc_180005644
0x180005633  lea     r9, [rsp+858h+Buffer]
0x180005638  lea     r8, aComoutofprocre; "ComOutOfProcRegisterClassObjects"
0x18000563f  call    McTemplateU0sz_EtwEventWriteTransfer
0x180005644  mov     rcx, cs:WPP_GLOBAL_Control
0x18000564b  lea     rax, WPP_GLOBAL_Control
0x180005652  cmp     rcx, rax
0x180005655  jz      short loc_180005675
0x180005657  test    byte ptr [rcx+1Ch], 1
0x18000565b  jz      short loc_180005675
0x18000565d  mov     rcx, [rcx+10h]
0x180005661  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180005668  mov     edx, 16h
0x18000566d  mov     r9d, ebx
0x180005670  call    WPP_SF_d
0x180005675  mov     eax, ebx
0x180005677  mov     rcx, [rsp+858h+var_18]
0x18000567f  xor     rcx, rsp; StackCookie
0x180005682  call    __security_check_cookie
0x180005687  add     rsp, 850h
0x18000568e  pop     rbx
0x18000568f  retn
```
