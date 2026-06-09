# CscStoreCleanup

- ea: `0x140022a0c`
- end: `0x140022b2f`
- name: `CscStoreCleanup`
- size: `291`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14002310c`
- `0x140090740`

## callees

- `0x1400169d4`
- `0x140022a0c`
- `0x14002f440`
- `0x1400548d0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140022a82`
- `ntoskrnl!ExDeleteResourceLite` at `0x140022aeb`
- `ntoskrnl!ExDeleteResourceLite` at `0x140022a82`
- `ntoskrnl!ExDeleteResourceLite` at `0x140022aeb`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140022aa9`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140022aa9`
- `ntoskrnl!RtlAssert` at `0x140022a64`
- `ntoskrnl!RtlAssert` at `0x140022a64`

## pseudocode

```c
void CscStoreCleanup()
{
  char v0; // cl

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_3bd1e00568fe30bc384778544301c268_Traceguids);
  if ( qword_14003BC08 )
    RtlAssert("!CscStoreIsAttached()", "base\\fs\\remotefs\\rdr\\csc\\newdb\\wrapper.c", 0xDEu, 0);
  v0 = byte_14003BC00;
  if ( (byte_14003BC00 & 1) != 0 )
  {
    ExDeleteResourceLite(&stru_14003BC10);
    v0 = byte_14003BC00;
  }
  if ( (v0 & 2) != 0 && !--dword_14003BD00 )
  {
    ExDeletePagedLookasideList(&Lookaside);
    memset(&dword_14003BD00, 0, 0xC0u);
    v0 = byte_14003BC00;
  }
  if ( (v0 & 4) != 0 )
  {
    CscEnMigCleanup();
    v0 = byte_14003BC00;
  }
  if ( (v0 & 8) != 0 )
    ExDeleteResourceLite(&stru_14003BE58);
  byte_14003BC00 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_3bd1e00568fe30bc384778544301c268_Traceguids);
}

```

## disassembly

```asm
0x140022a0c  push    rdi
0x140022a0e  sub     rsp, 20h
0x140022a12  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a19  lea     rdi, WPP_GLOBAL_Control
0x140022a20  cmp     rcx, rdi
0x140022a23  jz      short loc_140022A43
0x140022a25  test    dword ptr [rcx+2Ch], 40000h
0x140022a2c  jz      short loc_140022A43
0x140022a2e  mov     rcx, [rcx+18h]
0x140022a32  lea     r8, WPP_3bd1e00568fe30bc384778544301c268_Traceguids
0x140022a39  mov     edx, 0Ch
0x140022a3e  call    WPP_SF_
0x140022a43  cmp     cs:qword_14003BC08, 0
0x140022a4b  jz      short loc_140022A70
0x140022a4d  xor     r9d, r9d; MutableMessage
0x140022a50  lea     rdx, aBaseFsRemotefs_2; "base\\fs\\remotefs\\rdr\\csc\\newdb\\wr"...
0x140022a57  mov     r8d, 0DEh; LineNumber
0x140022a5d  lea     rcx, aCscstoreisatta; "!CscStoreIsAttached()"
0x140022a64  call    cs:__imp_RtlAssert
0x140022a6b  nop     dword ptr [rax+rax+00h]
0x140022a70  mov     cl, cs:byte_14003BC00
0x140022a76  test    cl, 1
0x140022a79  jz      short loc_140022A94
0x140022a7b  lea     rcx, stru_14003BC10; Resource
0x140022a82  call    cs:__imp_ExDeleteResourceLite
0x140022a89  nop     dword ptr [rax+rax+00h]
0x140022a8e  mov     cl, cs:byte_14003BC00
0x140022a94  test    cl, 2
0x140022a97  jz      short loc_140022ACF
0x140022a99  sub     cs:dword_14003BD00, 1
0x140022aa0  jnz     short loc_140022ACF
0x140022aa2  lea     rcx, Lookaside; Lookaside
0x140022aa9  call    cs:__imp_ExDeletePagedLookasideList
0x140022ab0  nop     dword ptr [rax+rax+00h]
0x140022ab5  xor     edx, edx; Val
0x140022ab7  lea     rcx, dword_14003BD00; void *
0x140022abe  mov     r8d, 0C0h; Size
0x140022ac4  call    memset
0x140022ac9  mov     cl, cs:byte_14003BC00
0x140022acf  test    cl, 4
0x140022ad2  jz      short loc_140022ADF
0x140022ad4  call    CscEnMigCleanup
0x140022ad9  mov     cl, cs:byte_14003BC00
0x140022adf  test    cl, 8
0x140022ae2  jz      short loc_140022AF7
0x140022ae4  lea     rcx, stru_14003BE58; Resource
0x140022aeb  call    cs:__imp_ExDeleteResourceLite
0x140022af2  nop     dword ptr [rax+rax+00h]
0x140022af7  mov     cs:byte_14003BC00, 0
0x140022afe  mov     rcx, cs:WPP_GLOBAL_Control
0x140022b05  cmp     rcx, rdi
0x140022b08  jz      short loc_140022B28
0x140022b0a  test    dword ptr [rcx+2Ch], 40000h
0x140022b11  jz      short loc_140022B28
0x140022b13  mov     rcx, [rcx+18h]
0x140022b17  lea     r8, WPP_3bd1e00568fe30bc384778544301c268_Traceguids
0x140022b1e  mov     edx, 0Dh
0x140022b23  call    WPP_SF_
0x140022b28  add     rsp, 20h
0x140022b2c  pop     rdi
0x140022b2d  retn
```
