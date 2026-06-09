# RtpGetComputerName

- ea: `0x180014388`
- end: `0x180014450`
- name: `RtpGetComputerName`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180013e88`

## callees

- `0x1800022d6`
- `0x1800087f8`
- `0x1800093d0`
- `0x180013c74`
- `0x180014388`
- `0x180021010`

## import_xrefs

- `msvcrt!free` at `0x18001443e`
- `msvcrt!free` at `0x18001443e`
- `mqsec!GetComputerNameInternal` at `0x1800143c6`
- `mqsec!GetComputerNameInternal` at `0x1800143c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void RtpGetComputerName()
{
  wchar_t *v0; // rbx
  int ComputerNameInternal; // edi
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( !g_lpwcsComputerName )
  {
    g_dwComputerNameLen = 16;
    v0 = (wchar_t *)MmAllocate(0x20u);
    ComputerNameInternal = GetComputerNameInternal(v0, &g_dwComputerNameLen);
    if ( ComputerNameInternal < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids,
          (unsigned int)ComputerNameInternal);
      LogMsgHR(ComputerNameInternal, (wchar_t *)L"rt/rtmain", 0x4BBu);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, ComputerNameInternal);
      throw (bad_hresult *)pExceptionObject;
    }
    g_lpwcsComputerName = v0;
    free(0);
  }
}

```

## disassembly

```asm
0x180014388  mov     [rsp+arg_8], rbx
0x18001438d  push    rdi
0x18001438e  sub     rsp, 40h
0x180014392  cmp     cs:?g_lpwcsComputerName@@3PEA_WEA, 0; wchar_t * g_lpwcsComputerName
0x18001439a  jnz     loc_180014445
0x1800143a0  mov     cs:?g_dwComputerNameLen@@3KA, 10h; ulong g_dwComputerNameLen
0x1800143aa  mov     ecx, 20h ; ' '; unsigned __int64
0x1800143af  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800143b4  mov     rbx, rax
0x1800143b7  mov     [rsp+48h+arg_0], rax
0x1800143bc  lea     rdx, ?g_dwComputerNameLen@@3KA; ulong g_dwComputerNameLen
0x1800143c3  mov     rcx, rax
0x1800143c6  call    cs:__imp_?GetComputerNameInternal@@YAJPEA_WPEAK@Z; GetComputerNameInternal(wchar_t *,ulong *)
0x1800143cc  mov     edi, eax
0x1800143ce  test    eax, eax
0x1800143d0  jns     short loc_180014435
0x1800143d2  lea     rax, WPP_GLOBAL_Control
0x1800143d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143e0  cmp     rcx, rax
0x1800143e3  jz      short loc_180014403
0x1800143e5  test    byte ptr [rcx+1Ch], 1
0x1800143e9  jz      short loc_180014403
0x1800143eb  mov     edx, 0Eh
0x1800143f0  mov     r9d, edi
0x1800143f3  lea     r8, WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids
0x1800143fa  mov     rcx, [rcx+10h]
0x1800143fe  call    WPP_SF_d
0x180014403  mov     r8d, 4BBh; unsigned __int16
0x180014409  lea     rdx, aRtRtmain; "rt/rtmain"
0x180014410  mov     ecx, edi; int
0x180014412  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180014417  mov     edx, edi; unsigned int
0x180014419  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001441e  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180014423  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x18001442a  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001442f  call    _CxxThrowException_0
0x180014435  mov     cs:?g_lpwcsComputerName@@3PEA_WEA, rbx; wchar_t * g_lpwcsComputerName
0x18001443c  xor     ecx, ecx; Block
0x18001443e  call    cs:__imp_free
0x180014444  nop
0x180014445  mov     rbx, [rsp+48h+arg_8]
0x18001444a  add     rsp, 40h
0x18001444e  pop     rdi
0x18001444f  retn
```
