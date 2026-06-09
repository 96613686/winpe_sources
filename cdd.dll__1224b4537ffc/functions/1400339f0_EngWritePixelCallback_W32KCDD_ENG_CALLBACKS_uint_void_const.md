# EngWritePixelCallback(_W32KCDD_ENG_CALLBACKS *,uint,void * const)

- ea: `0x1400339f0`
- end: `0x140033da7`
- name: `?EngWritePixelCallback@@YAXPEAU_W32KCDD_ENG_CALLBACKS@@IQEAX@Z`
- size: `951`
- prototype: `void __fastcall(struct _W32KCDD_ENG_CALLBACKS *, unsigned int, void *const)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000df80`
- `0x14000fdb0`
- `0x14001d488`
- `0x1400339f0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140033a2a`
- `ntoskrnl!DbgPrint` at `0x140033aa9`
- `ntoskrnl!DbgPrint` at `0x140033b17`
- `ntoskrnl!DbgPrint` at `0x140033b85`
- `ntoskrnl!DbgPrint` at `0x140033c74`
- `ntoskrnl!DbgPrint` at `0x140033a2a`
- `ntoskrnl!DbgPrint` at `0x140033aa9`
- `ntoskrnl!DbgPrint` at `0x140033b17`
- `ntoskrnl!DbgPrint` at `0x140033b85`
- `ntoskrnl!DbgPrint` at `0x140033c74`
- `ntoskrnl!KdDebuggerEnabled` at `0x140033a17`
- `ntoskrnl!KdDebuggerEnabled` at `0x140033a96`
- `ntoskrnl!KdDebuggerEnabled` at `0x140033b04`
- `ntoskrnl!KdDebuggerEnabled` at `0x140033b72`
- `ntoskrnl!KdDebuggerEnabled` at `0x140033c61`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033a50`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033acf`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033b3d`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033bab`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033c9c`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033a50`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033acf`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033b3d`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033bab`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033c9c`
- `watchdog!WdLogSingleEntry0` at `0x140033a39`
- `watchdog!WdLogSingleEntry0` at `0x140033ab8`
- `watchdog!WdLogSingleEntry0` at `0x140033b26`
- `watchdog!WdLogSingleEntry0` at `0x140033b94`
- `watchdog!WdLogSingleEntry0` at `0x140033c83`
- `watchdog!WdLogSingleEntry0` at `0x140033a39`
- `watchdog!WdLogSingleEntry0` at `0x140033ab8`
- `watchdog!WdLogSingleEntry0` at `0x140033b26`
- `watchdog!WdLogSingleEntry0` at `0x140033b94`
- `watchdog!WdLogSingleEntry0` at `0x140033c83`

## string_xrefs

- `0x140033c6d`: `Error submitting ColorFill command`
- `0x140033a23`: `WriteAddress is wrong in EngWritePixelCallback`
- `0x140033aa2`: `Wrong surface offset in EngWritePixelCallback`
- `0x140033b10`: `X is wrong in EngWritePixelCallback`
- `0x140033b7e`: `Y is wrong in EngWritePixelCallback`

## pseudocode

```c
void __fastcall EngWritePixelCallback(struct _W32KCDD_ENG_CALLBACKS *a1, __int64 a2, unsigned __int64 a3)
{
  int v3; // esi
  _QWORD *v5; // rax
  unsigned int v6; // esi
  __int64 v7; // rbp
  unsigned int v8; // edi
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  unsigned int v12; // eax
  const struct tagRECT **v13; // rsi
  __int64 v14; // r15
  const struct tagRECT *v15; // r9
  unsigned int v16; // r8d
  _QWORD *v17; // rax
  const struct tagRECT *v18; // r8
  __int64 top; // r10
  __int64 v20; // r11
  const struct tagRECT *v21; // r9
  __int64 right; // r9
  __int64 left; // r9
  __int64 bottom; // rcx
  _BYTE v25[72]; // [rsp+20h] [rbp-48h] BYREF

  v3 = a3;
  if ( a3 < *((_QWORD *)a1 + 15) && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("WriteAddress is wrong in EngWritePixelCallback");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 249;
    v5 = (_QWORD *)WdLogNewEntry5_WdError();
    v5[3] = gCddImageInfo;
    v5[4] = (unsigned int)dword_14003E570;
    v5[5] = 215857758;
    WdLogGlobalForLineNumber = 249;
    __debugbreak();
  }
  v6 = v3 - *((_DWORD *)a1 + 30);
  v7 = v6 / *((_DWORD *)a1 + 32);
  v8 = (v6 % *((_DWORD *)a1 + 32)) >> 2;
  if ( (v6 & 3) != 0 && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("Wrong surface offset in EngWritePixelCallback");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 253;
    v9 = (_QWORD *)WdLogNewEntry5_WdError();
    v9[3] = gCddImageInfo;
    v9[4] = (unsigned int)dword_14003E570;
    v9[5] = 215857758;
    WdLogGlobalForLineNumber = 253;
    __debugbreak();
  }
  if ( v8 >= *(_DWORD *)(*((_QWORD *)a1 + 12) + 16LL) && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("X is wrong in EngWritePixelCallback");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 254;
    v10 = (_QWORD *)WdLogNewEntry5_WdError();
    v10[3] = gCddImageInfo;
    v10[4] = (unsigned int)dword_14003E570;
    v10[5] = 215857758;
    WdLogGlobalForLineNumber = 254;
    __debugbreak();
  }
  if ( (unsigned int)v7 >= *(_DWORD *)(*((_QWORD *)a1 + 12) + 20LL) && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("Y is wrong in EngWritePixelCallback");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 255;
    v11 = (_QWORD *)WdLogNewEntry5_WdError();
    v11[3] = gCddImageInfo;
    v11[4] = (unsigned int)dword_14003E570;
    v11[5] = 215857758;
    WdLogGlobalForLineNumber = 255;
    __debugbreak();
  }
  v12 = *((_DWORD *)a1 + 36);
  v13 = (const struct tagRECT **)((char *)a1 + 136);
  if ( v12 >= *((_DWORD *)a1 + 37) )
  {
    v14 = *(_QWORD *)(*((_QWORD *)a1 + 12) + 8LL);
    CCommandBufferMutex::CCommandBufferMutex((CCommandBufferMutex *)v25, (struct CDDPDEV *)v14, 0, 0);
    v15 = *v13;
    v16 = *((_DWORD *)a1 + 36);
    *((_QWORD *)a1 + 6) = v25;
    if ( !(unsigned int)CHwCommandBuffer::AddColorFillCommand(
                          *(CDDPDEV ***)(v14 + 12696),
                          (struct _W32KCDD_ENG_CALLBACKS *)((char *)a1 + 16),
                          v16,
                          v15)
      && !(unsigned int)CHwCommandBuffer::AddColorFillCommand(
                          *(CDDPDEV ***)(v14 + 12696),
                          (struct _W32KCDD_ENG_CALLBACKS *)((char *)a1 + 16),
                          *((_DWORD *)a1 + 36),
                          *v13)
      && (*(_DWORD *)(v14 + 2744) & 0x400) == 0
      && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error submitting ColorFill command");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 266;
      v17 = (_QWORD *)WdLogNewEntry5_WdError();
      v17[3] = gCddImageInfo;
      v17[4] = (unsigned int)dword_14003E570;
      v17[5] = 215857758;
      WdLogGlobalForLineNumber = 266;
      __debugbreak();
    }
    CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)v25);
    v12 = 0;
    *((_DWORD *)a1 + 36) = 0;
  }
  v18 = *v13;
  if ( v12 )
  {
    top = v18[v12 - 1].top;
    v20 = (unsigned int)(v7 + 1);
    v21 = &v18[v12];
    if ( v7 == top && v20 == v21[-1].bottom )
    {
      right = v18[v12 - 1].right;
      if ( v8 == right )
      {
        v18[v12 - 1].right = right + 1;
        return;
      }
      left = v18[v12 - 1].left;
      if ( v8 + 1 == left )
      {
        v18[v12 - 1].left = left - 1;
        return;
      }
    }
    else if ( v8 == (__int64)v18[v12 - 1].left && v8 + 1 == (__int64)v18[v12 - 1].right )
    {
      bottom = v21[-1].bottom;
      if ( v7 == bottom )
      {
        v21[-1].bottom = bottom + 1;
        return;
      }
      if ( v20 == top )
      {
        v18[v12 - 1].top = top - 1;
        return;
      }
    }
  }
  v18[v12].left = v8;
  v18[v12].right = v8 + 1;
  v18[v12].bottom = v7 + 1;
  v18[v12].top = v7;
  ++*((_DWORD *)a1 + 36);
}

```

## disassembly

```asm
0x1400339f0  push    rbx
0x1400339f2  push    rbp
0x1400339f3  push    rsi
0x1400339f4  push    rdi
0x1400339f5  push    r13
0x1400339f7  push    r14
0x1400339f9  push    r15
0x1400339fb  sub     rsp, 30h
0x1400339ff  mov     rsi, r8
0x140033a02  mov     rbx, rcx
0x140033a05  mov     r13d, 2
0x140033a0b  mov     r15d, 0CDDBA5Eh
0x140033a11  cmp     r8, [rcx+78h]
0x140033a15  jnb     short loc_140033A7C
0x140033a17  mov     rax, cs:KdDebuggerEnabled
0x140033a1e  cmp     byte ptr [rax], 0
0x140033a21  jz      short loc_140033A7C
0x140033a23  lea     rcx, aWriteaddressIs; "WriteAddress is wrong in EngWritePixelC"...
0x140033a2a  call    cs:__imp_DbgPrint
0x140033a31  nop     dword ptr [rax+rax+00h]
0x140033a36  mov     ecx, r13d
0x140033a39  call    cs:__imp_WdLogSingleEntry0
0x140033a40  nop     dword ptr [rax+rax+00h]
0x140033a45  mov     edi, 0F9h
0x140033a4a  mov     cs:WdLogGlobalForLineNumber, edi
0x140033a50  call    cs:__imp_WdLogNewEntry5_WdError
0x140033a57  nop     dword ptr [rax+rax+00h]
0x140033a5c  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140033a63  mov     [rax+18h], rcx
0x140033a67  mov     ecx, cs:dword_14003E570
0x140033a6d  mov     [rax+20h], rcx
0x140033a71  mov     [rax+28h], r15
0x140033a75  mov     cs:WdLogGlobalForLineNumber, edi
0x140033a7b  int     3; Trap to Debugger
0x140033a7c  sub     esi, [rbx+78h]
0x140033a7f  xor     edx, edx
0x140033a81  mov     eax, esi
0x140033a83  div     dword ptr [rbx+80h]
0x140033a89  mov     edi, edx
0x140033a8b  mov     ebp, eax
0x140033a8d  shr     edi, 2
0x140033a90  test    sil, 3
0x140033a94  jz      short loc_140033AFB
0x140033a96  mov     rcx, cs:KdDebuggerEnabled
0x140033a9d  cmp     byte ptr [rcx], 0
0x140033aa0  jz      short loc_140033AFB
0x140033aa2  lea     rcx, aWrongSurfaceOf; "Wrong surface offset in EngWritePixelCa"...
0x140033aa9  call    cs:__imp_DbgPrint
0x140033ab0  nop     dword ptr [rax+rax+00h]
0x140033ab5  mov     ecx, r13d
0x140033ab8  call    cs:__imp_WdLogSingleEntry0
0x140033abf  nop     dword ptr [rax+rax+00h]
0x140033ac4  mov     esi, 0FDh
0x140033ac9  mov     cs:WdLogGlobalForLineNumber, esi
0x140033acf  call    cs:__imp_WdLogNewEntry5_WdError
0x140033ad6  nop     dword ptr [rax+rax+00h]
0x140033adb  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140033ae2  mov     [rax+18h], rcx
0x140033ae6  mov     ecx, cs:dword_14003E570
0x140033aec  mov     [rax+20h], rcx
0x140033af0  mov     [rax+28h], r15
0x140033af4  mov     cs:WdLogGlobalForLineNumber, esi
0x140033afa  int     3; Trap to Debugger
0x140033afb  mov     rax, [rbx+60h]
0x140033aff  cmp     edi, [rax+10h]
0x140033b02  jb      short loc_140033B69
0x140033b04  mov     rax, cs:KdDebuggerEnabled
0x140033b0b  cmp     byte ptr [rax], 0
0x140033b0e  jz      short loc_140033B69
0x140033b10  lea     rcx, aXIsWrongInEngw; "X is wrong in EngWritePixelCallback"
0x140033b17  call    cs:__imp_DbgPrint
0x140033b1e  nop     dword ptr [rax+rax+00h]
0x140033b23  mov     ecx, r13d
0x140033b26  call    cs:__imp_WdLogSingleEntry0
0x140033b2d  nop     dword ptr [rax+rax+00h]
0x140033b32  mov     esi, 0FEh
0x140033b37  mov     cs:WdLogGlobalForLineNumber, esi
0x140033b3d  call    cs:__imp_WdLogNewEntry5_WdError
0x140033b44  nop     dword ptr [rax+rax+00h]
0x140033b49  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140033b50  mov     [rax+18h], rcx
0x140033b54  mov     ecx, cs:dword_14003E570
0x140033b5a  mov     [rax+20h], rcx
0x140033b5e  mov     [rax+28h], r15
0x140033b62  mov     cs:WdLogGlobalForLineNumber, esi
0x140033b68  int     3; Trap to Debugger
0x140033b69  mov     rax, [rbx+60h]
0x140033b6d  cmp     ebp, [rax+14h]
0x140033b70  jb      short loc_140033BD7
0x140033b72  mov     rax, cs:KdDebuggerEnabled
0x140033b79  cmp     byte ptr [rax], 0
0x140033b7c  jz      short loc_140033BD7
0x140033b7e  lea     rcx, aYIsWrongInEngw; "Y is wrong in EngWritePixelCallback"
0x140033b85  call    cs:__imp_DbgPrint
0x140033b8c  nop     dword ptr [rax+rax+00h]
0x140033b91  mov     ecx, r13d
0x140033b94  call    cs:__imp_WdLogSingleEntry0
0x140033b9b  nop     dword ptr [rax+rax+00h]
0x140033ba0  mov     esi, 0FFh
0x140033ba5  mov     cs:WdLogGlobalForLineNumber, esi
0x140033bab  call    cs:__imp_WdLogNewEntry5_WdError
0x140033bb2  nop     dword ptr [rax+rax+00h]
0x140033bb7  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140033bbe  mov     [rax+18h], rcx
0x140033bc2  mov     ecx, cs:dword_14003E570
0x140033bc8  mov     [rax+20h], rcx
0x140033bcc  mov     [rax+28h], r15
0x140033bd0  mov     cs:WdLogGlobalForLineNumber, esi
0x140033bd6  int     3; Trap to Debugger
0x140033bd7  mov     eax, [rbx+90h]
0x140033bdd  lea     rsi, [rbx+88h]
0x140033be4  cmp     eax, [rbx+94h]
0x140033bea  jb      loc_140033CE3
0x140033bf0  mov     rax, [rbx+60h]
0x140033bf4  lea     rcx, [rsp+68h+var_48]; this
0x140033bf9  xor     r9d, r9d; unsigned __int8
0x140033bfc  xor     r8d, r8d; unsigned __int8
0x140033bff  mov     r15, [rax+8]
0x140033c03  mov     rdx, r15; struct CDDPDEV *
0x140033c06  call    ??0CCommandBufferMutex@@QEAA@PEAUCDDPDEV@@EE@Z; CCommandBufferMutex::CCommandBufferMutex(CDDPDEV *,uchar,uchar)
0x140033c0b  mov     r9, [rsi]; struct tagRECT *
0x140033c0e  lea     rax, [rsp+68h+var_48]
0x140033c13  mov     r8d, [rbx+90h]; unsigned int
0x140033c1a  lea     rdx, [rbx+10h]; struct COLORFILL_DATA *
0x140033c1e  mov     [rbx+30h], rax
0x140033c22  mov     rcx, [r15+3198h]; this
0x140033c29  call    ?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)
0x140033c2e  test    eax, eax
0x140033c30  jnz     loc_140033CCD
0x140033c36  mov     r9, [rsi]; struct tagRECT *
0x140033c39  lea     rdx, [rbx+10h]; struct COLORFILL_DATA *
0x140033c3d  mov     r8d, [rbx+90h]; unsigned int
0x140033c44  mov     rcx, [r15+3198h]; this
0x140033c4b  call    ?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)
0x140033c50  test    eax, eax
0x140033c52  jnz     short loc_140033CCD
0x140033c54  test    dword ptr [r15+0AB8h], 400h
0x140033c5f  jnz     short loc_140033CCD
0x140033c61  mov     rax, cs:KdDebuggerEnabled
0x140033c68  cmp     byte ptr [rax], 0
0x140033c6b  jz      short loc_140033CCD
0x140033c6d  lea     rcx, aErrorSubmittin_2; "Error submitting ColorFill command"
0x140033c74  call    cs:__imp_DbgPrint
0x140033c7b  nop     dword ptr [rax+rax+00h]
0x140033c80  mov     ecx, r13d
0x140033c83  call    cs:__imp_WdLogSingleEntry0
0x140033c8a  nop     dword ptr [rax+rax+00h]
0x140033c8f  mov     r14d, 10Ah
0x140033c95  mov     cs:WdLogGlobalForLineNumber, r14d
0x140033c9c  call    cs:__imp_WdLogNewEntry5_WdError
0x140033ca3  nop     dword ptr [rax+rax+00h]
0x140033ca8  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140033caf  mov     [rax+18h], rcx
0x140033cb3  mov     ecx, cs:dword_14003E570
0x140033cb9  mov     [rax+20h], rcx
0x140033cbd  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140033cc5  mov     cs:WdLogGlobalForLineNumber, r14d
0x140033ccc  int     3; Trap to Debugger
0x140033ccd  lea     rcx, [rsp+68h+var_48]; this
0x140033cd2  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x140033cd7  xor     eax, eax
0x140033cd9  mov     dword ptr [rbx+90h], 0
0x140033ce3  mov     r8, [rsi]
0x140033ce6  mov     edx, eax
0x140033ce8  add     rdx, rdx
0x140033ceb  test    eax, eax
0x140033ced  jz      loc_140033D78
0x140033cf3  movsxd  r10, dword ptr [r8+rdx*8-0Ch]
0x140033cf8  lea     r11d, [rbp+1]
0x140033cfc  lea     r9, [r8+rdx*8]
0x140033d00  cmp     rbp, r10
0x140033d03  jnz     short loc_140033D3D
0x140033d05  movsxd  rax, dword ptr [r9-4]
0x140033d09  cmp     r11, rax
0x140033d0c  jnz     short loc_140033D3D
0x140033d0e  movsxd  r9, dword ptr [r8+rdx*8-8]
0x140033d13  mov     ecx, edi
0x140033d15  cmp     rcx, r9
0x140033d18  jnz     short loc_140033D25
0x140033d1a  lea     eax, [r9+1]
0x140033d1e  mov     [r8+rdx*8-8], eax
0x140033d23  jmp     short loc_140033D97
0x140033d25  movsxd  r9, dword ptr [r8+rdx*8-10h]
0x140033d2a  lea     ecx, [rdi+1]
0x140033d2d  cmp     rcx, r9
0x140033d30  jnz     short loc_140033D78
0x140033d32  lea     eax, [r9-1]
0x140033d36  mov     [r8+rdx*8-10h], eax
0x140033d3b  jmp     short loc_140033D97
0x140033d3d  movsxd  rax, dword ptr [r8+rdx*8-10h]
0x140033d42  mov     ecx, edi
0x140033d44  cmp     rcx, rax
0x140033d47  jnz     short loc_140033D78
0x140033d49  movsxd  rax, dword ptr [r8+rdx*8-8]
0x140033d4e  lea     ecx, [rdi+1]
0x140033d51  cmp     rcx, rax
0x140033d54  jnz     short loc_140033D78
0x140033d56  movsxd  rcx, dword ptr [r9-4]
0x140033d5a  cmp     rbp, rcx
0x140033d5d  jnz     short loc_140033D68
0x140033d5f  lea     eax, [rcx+1]
0x140033d62  mov     [r9-4], eax
0x140033d66  jmp     short loc_140033D97
0x140033d68  cmp     r11, r10
0x140033d6b  jnz     short loc_140033D78
0x140033d6d  lea     eax, [r10-1]
0x140033d71  mov     [r8+rdx*8-0Ch], eax
0x140033d76  jmp     short loc_140033D97
0x140033d78  lea     eax, [rdi+1]
0x140033d7b  mov     [r8+rdx*8], edi
0x140033d7f  mov     [r8+rdx*8+8], eax
0x140033d84  lea     eax, [rbp+1]
0x140033d87  mov     [r8+rdx*8+0Ch], eax
0x140033d8c  mov     [r8+rdx*8+4], ebp
0x140033d91  inc     dword ptr [rbx+90h]
0x140033d97  add     rsp, 30h
0x140033d9b  pop     r15
0x140033d9d  pop     r14
0x140033d9f  pop     r13
0x140033da1  pop     rdi
0x140033da2  pop     rsi
0x140033da3  pop     rbp
0x140033da4  pop     rbx
0x140033da5  retn
```
