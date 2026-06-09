# InitServiceName

- ea: `0x180013af4`
- end: `0x180013bb6`
- name: `InitServiceName`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180013e88`

## callees

- `0x1800022d6`
- `0x1800087f8`
- `0x1800093d0`
- `0x180013af4`
- `0x180013c74`
- `0x1800144c8`

## import_xrefs

- `msvcrt!free` at `0x180013ba9`
- `msvcrt!free` at `0x180013ba9`
- `KERNEL32!TlsGetValue` at `0x180013b16`
- `KERNEL32!TlsGetValue` at `0x180013b16`
- `mqsec!SetFalconServiceName` at `0x180013b97`
- `mqsec!SetFalconServiceName` at `0x180013b97`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void InitServiceName()
{
  void *Value; // rax
  int v1; // ebx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  void *Block; // [rsp+50h] [rbp+8h] BYREF

  if ( !byte_18003DD1B )
  {
    Block = 0;
    Value = TlsGetValue(g_hBindIndex);
    v1 = RtpQMGetMsmqServiceName(Value, (wchar_t **)&Block);
    if ( v1 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids,
          (unsigned int)v1);
      LogMsgHR(v1, (wchar_t *)L"rt/rtmain", 0x4BCu);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v1);
      throw (bad_hresult *)pExceptionObject;
    }
    SetFalconServiceName((const wchar_t *)Block);
    byte_18003DD1B = 1;
    free(Block);
  }
}

```

## disassembly

```asm
0x180013af4  push    rbx
0x180013af6  sub     rsp, 40h
0x180013afa  cmp     cs:byte_18003DD1B, 0
0x180013b01  jnz     loc_180013BB0
0x180013b07  mov     [rsp+48h+Block], 0
0x180013b10  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x180013b16  call    cs:__imp_TlsGetValue
0x180013b1c  lea     rdx, [rsp+48h+Block]; wchar_t **
0x180013b21  mov     rcx, rax; void *
0x180013b24  call    ?RtpQMGetMsmqServiceName@@YAJPEAXPEAPEA_W@Z; RtpQMGetMsmqServiceName(void *,wchar_t * *)
0x180013b29  mov     ebx, eax
0x180013b2b  test    eax, eax
0x180013b2d  jns     short loc_180013B92
0x180013b2f  lea     rax, WPP_GLOBAL_Control
0x180013b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b3d  cmp     rcx, rax
0x180013b40  jz      short loc_180013B60
0x180013b42  test    byte ptr [rcx+1Ch], 1
0x180013b46  jz      short loc_180013B60
0x180013b48  mov     edx, 0Fh
0x180013b4d  mov     r9d, ebx
0x180013b50  lea     r8, WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids
0x180013b57  mov     rcx, [rcx+10h]
0x180013b5b  call    WPP_SF_d
0x180013b60  mov     r8d, 4BCh; unsigned __int16
0x180013b66  lea     rdx, aRtRtmain; "rt/rtmain"
0x180013b6d  mov     ecx, ebx; int
0x180013b6f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180013b74  mov     edx, ebx; unsigned int
0x180013b76  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180013b7b  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180013b80  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180013b87  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180013b8c  call    _CxxThrowException_0
0x180013b92  mov     rcx, [rsp+48h+Block]
0x180013b97  call    cs:__imp_?SetFalconServiceName@@YAXPEB_W@Z; SetFalconServiceName(wchar_t const *)
0x180013b9d  mov     cs:byte_18003DD1B, 1
0x180013ba4  mov     rcx, [rsp+48h+Block]; Block
0x180013ba9  call    cs:__imp_free
0x180013baf  nop
0x180013bb0  add     rsp, 40h
0x180013bb4  pop     rbx
0x180013bb5  retn
```
