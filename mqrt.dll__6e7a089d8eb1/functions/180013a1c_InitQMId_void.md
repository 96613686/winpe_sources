# InitQMId(void)

- ea: `0x180013a1c`
- end: `0x180013aec`
- name: `?InitQMId@@YAXXZ`
- size: `208`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180013e88`

## callees

- `0x1800022d6`
- `0x1800087f8`
- `0x1800093d0`
- `0x180013a1c`
- `0x180013d20`

## import_xrefs

- `mqsec!GetFalconKeyValue` at `0x180013a5d`
- `mqsec!GetFalconKeyValue` at `0x180013a5d`

## string_xrefs

- `0x180013a56`: `MachineCache\QMId`

## pseudocode

```c
void InitQMId(void)
{
  int FalconKeyValue; // ebx
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v2; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v3; // [rsp+68h] [rbp+10h] BYREF

  if ( !g_fQMIdInit )
  {
    v3 = 3;
    v2 = 16;
    FalconKeyValue = GetFalconKeyValue(L"MachineCache\\QMId", &v3, &g_QMId, &v2, 0);
    if ( FalconKeyValue )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          16,
          &WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids,
          (unsigned int)FalconKeyValue);
      LogMsgNTStatus(FalconKeyValue, (wchar_t *)L"rt/rtmain", 0x4C6u);
      if ( FalconKeyValue > 0 )
        FalconKeyValue = (unsigned __int16)FalconKeyValue | 0x80070000;
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, FalconKeyValue);
      throw (bad_hresult *)pExceptionObject;
    }
    g_fQMIdInit = 1;
  }
}

```

## disassembly

```asm
0x180013a1c  mov     rax, rsp
0x180013a1f  push    rbx
0x180013a20  sub     rsp, 50h
0x180013a24  cmp     cs:?g_fQMIdInit@@3_NA, 0; bool g_fQMIdInit
0x180013a2b  jnz     loc_180013AE6
0x180013a31  lea     r9, [rax+8]
0x180013a35  mov     dword ptr [rax+10h], 3
0x180013a3c  lea     r8, ?g_QMId@@3U_GUID@@A; _GUID g_QMId
0x180013a43  mov     dword ptr [rax+8], 10h
0x180013a4a  lea     rdx, [rax+10h]
0x180013a4e  mov     qword ptr [rax-38h], 0
0x180013a56  lea     rcx, aMachinecacheQm; "MachineCache\\QMId"
0x180013a5d  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180013a63  mov     ebx, eax
0x180013a65  test    eax, eax
0x180013a67  jz      short loc_180013ADF
0x180013a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a70  lea     rax, WPP_GLOBAL_Control
0x180013a77  cmp     rcx, rax
0x180013a7a  jz      short loc_180013AA0
0x180013a7c  test    byte ptr [rcx+0BCh], 1
0x180013a83  jz      short loc_180013AA0
0x180013a85  mov     rcx, [rcx+0B0h]
0x180013a8c  lea     r8, WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids
0x180013a93  mov     edx, 10h
0x180013a98  mov     r9d, ebx
0x180013a9b  call    WPP_SF_d
0x180013aa0  mov     r8d, 4C6h; unsigned __int16
0x180013aa6  lea     rdx, aRtRtmain; "rt/rtmain"
0x180013aad  mov     ecx, ebx; int
0x180013aaf  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180013ab4  test    ebx, ebx
0x180013ab6  jle     short loc_180013AC1
0x180013ab8  movzx   ebx, bx
0x180013abb  or      ebx, 80070000h
0x180013ac1  mov     edx, ebx; unsigned int
0x180013ac3  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180013ac8  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180013acd  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180013ad4  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180013ad9  call    _CxxThrowException_0
0x180013adf  mov     cs:?g_fQMIdInit@@3_NA, 1; bool g_fQMIdInit
0x180013ae6  add     rsp, 50h
0x180013aea  pop     rbx
0x180013aeb  retn
```
