# EngFillRectCallback(_W32KCDD_ENG_CALLBACKS *,uint,tagRECT const *)

- ea: `0x140033800`
- end: `0x1400339e5`
- name: `?EngFillRectCallback@@YAXPEAU_W32KCDD_ENG_CALLBACKS@@IPEBUtagRECT@@@Z`
- size: `485`
- prototype: `void __fastcall(struct _W32KCDD_ENG_CALLBACKS *, unsigned int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000df80`
- `0x14000fdb0`
- `0x14001d488`
- `0x140033800`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140033851`
- `ntoskrnl!DbgPrint` at `0x140033946`
- `ntoskrnl!DbgPrint` at `0x140033851`
- `ntoskrnl!DbgPrint` at `0x140033946`
- `ntoskrnl!KdDebuggerEnabled` at `0x14003383e`
- `ntoskrnl!KdDebuggerEnabled` at `0x140033933`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033879`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003396e`
- `watchdog!WdLogNewEntry5_WdError` at `0x140033879`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003396e`
- `watchdog!WdLogSingleEntry0` at `0x140033862`
- `watchdog!WdLogSingleEntry0` at `0x140033957`
- `watchdog!WdLogSingleEntry0` at `0x140033862`
- `watchdog!WdLogSingleEntry0` at `0x140033957`

## string_xrefs

- `0x14003393f`: `Error submitting ColorFill command`

## pseudocode

```c
void __fastcall EngFillRectCallback(struct _W32KCDD_ENG_CALLBACKS *a1, __int64 a2, const struct tagRECT *a3)
{
  LONG right; // r9d
  LONG left; // r8d
  LONG bottom; // ecx
  LONG top; // edx
  LONG *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rsi
  const struct tagRECT *v15; // r9
  unsigned int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  _BYTE v20[56]; // [rsp+20h] [rbp-38h] BYREF

  right = a3->right;
  left = a3->left;
  if ( left > right
    || (bottom = a3->bottom, top = a3->top, top > bottom)
    || (v9 = (LONG *)*((_QWORD *)a1 + 4), left < *v9)
    || right > v9[2]
    || top < v9[1]
    || bottom > v9[3] )
  {
    if ( (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Invalid rect in EngFillRectCallback");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 326;
      v12 = (_QWORD *)WdLogNewEntry5_WdError(v11, v10);
      v12[3] = gCddImageInfo;
      v12[4] = (unsigned int)dword_14003E570;
      v12[5] = 215857758;
      WdLogGlobalForLineNumber = 326;
      __debugbreak();
    }
  }
  v13 = *((_DWORD *)a1 + 36);
  if ( v13 >= *((_DWORD *)a1 + 37) )
  {
    v14 = *(_QWORD *)(*((_QWORD *)a1 + 12) + 8LL);
    CCommandBufferMutex::CCommandBufferMutex((CCommandBufferMutex *)v20, (struct _KTHREAD **)v14, 0, 0);
    v15 = (const struct tagRECT *)*((_QWORD *)a1 + 17);
    v16 = *((_DWORD *)a1 + 36);
    *((_QWORD *)a1 + 6) = v20;
    if ( !(unsigned int)CHwCommandBuffer::AddColorFillCommand(
                          *(CDDPDEV ***)(v14 + 12696),
                          (struct _W32KCDD_ENG_CALLBACKS *)((char *)a1 + 16),
                          v16,
                          v15)
      && !(unsigned int)CHwCommandBuffer::AddColorFillCommand(
                          *(CDDPDEV ***)(v14 + 12696),
                          (struct _W32KCDD_ENG_CALLBACKS *)((char *)a1 + 16),
                          *((_DWORD *)a1 + 36),
                          *((const struct tagRECT **)a1 + 17))
      && (*(_DWORD *)(v14 + 2744) & 0x400) == 0
      && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error submitting ColorFill command");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 337;
      v19 = (_QWORD *)WdLogNewEntry5_WdError(v18, v17);
      v19[3] = gCddImageInfo;
      v19[4] = (unsigned int)dword_14003E570;
      v19[5] = 215857758;
      WdLogGlobalForLineNumber = 337;
      __debugbreak();
    }
    CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)v20);
    *(_OWORD *)*((_QWORD *)a1 + 17) = 0;
    *((_DWORD *)a1 + 36) = 0;
    v13 = 0;
  }
  *(struct tagRECT *)(*((_QWORD *)a1 + 17) + 16LL * v13) = *a3;
  ++*((_DWORD *)a1 + 36);
}

```

## disassembly

```asm
0x140033800  push    rbx
0x140033802  push    rbp
0x140033803  push    rsi
0x140033804  push    rdi
0x140033805  sub     rsp, 38h
0x140033809  mov     r9d, [r8+8]
0x14003380d  mov     rdi, r8
0x140033810  mov     r8d, [r8]
0x140033813  mov     rbx, rcx
0x140033816  cmp     r8d, r9d
0x140033819  jg      short loc_14003383E
0x14003381b  mov     ecx, [rdi+0Ch]
0x14003381e  mov     edx, [rdi+4]
0x140033821  cmp     edx, ecx
0x140033823  jg      short loc_14003383E
0x140033825  mov     rax, [rbx+20h]
0x140033829  cmp     r8d, [rax]
0x14003382c  jl      short loc_14003383E
0x14003382e  cmp     r9d, [rax+8]
0x140033832  jg      short loc_14003383E
0x140033834  cmp     edx, [rax+4]
0x140033837  jl      short loc_14003383E
0x140033839  cmp     ecx, [rax+0Ch]
0x14003383c  jle     short loc_1400338A9
0x14003383e  mov     rax, cs:KdDebuggerEnabled
0x140033845  cmp     byte ptr [rax], 0
0x140033848  jz      short loc_1400338A9
0x14003384a  lea     rcx, aInvalidRectInE; "Invalid rect in EngFillRectCallback"
0x140033851  call    cs:__imp_DbgPrint
0x140033858  nop     dword ptr [rax+rax+00h]
0x14003385d  mov     ecx, 2
0x140033862  call    cs:__imp_WdLogSingleEntry0
0x140033869  nop     dword ptr [rax+rax+00h]
0x14003386e  mov     esi, 146h
0x140033873  mov     cs:WdLogGlobalForLineNumber, esi
0x140033879  call    cs:__imp_WdLogNewEntry5_WdError
0x140033880  nop     dword ptr [rax+rax+00h]
0x140033885  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14003388c  mov     [rax+18h], rcx
0x140033890  mov     ecx, cs:dword_14003E570
0x140033896  mov     [rax+20h], rcx
0x14003389a  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400338a2  mov     cs:WdLogGlobalForLineNumber, esi
0x1400338a8  int     3; Trap to Debugger
0x1400338a9  mov     eax, [rbx+90h]
0x1400338af  cmp     eax, [rbx+94h]
0x1400338b5  jb      loc_1400339C1
0x1400338bb  mov     rax, [rbx+60h]
0x1400338bf  lea     rcx, [rsp+58h+var_38]; this
0x1400338c4  xor     r9d, r9d; unsigned __int8
0x1400338c7  xor     r8d, r8d; unsigned __int8
0x1400338ca  mov     rsi, [rax+8]
0x1400338ce  mov     rdx, rsi; struct CDDPDEV *
0x1400338d1  call    ??0CCommandBufferMutex@@QEAA@PEAUCDDPDEV@@EE@Z; CCommandBufferMutex::CCommandBufferMutex(CDDPDEV *,uchar,uchar)
0x1400338d6  mov     r9, [rbx+88h]; struct tagRECT *
0x1400338dd  lea     rax, [rsp+58h+var_38]
0x1400338e2  mov     r8d, [rbx+90h]; unsigned int
0x1400338e9  lea     rdx, [rbx+10h]; struct COLORFILL_DATA *
0x1400338ed  mov     [rbx+30h], rax
0x1400338f1  mov     rcx, [rsi+3198h]; this
0x1400338f8  call    ?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)
0x1400338fd  test    eax, eax
0x1400338ff  jnz     loc_14003399E
0x140033905  mov     r9, [rbx+88h]; struct tagRECT *
0x14003390c  lea     rdx, [rbx+10h]; struct COLORFILL_DATA *
0x140033910  mov     r8d, [rbx+90h]; unsigned int
0x140033917  mov     rcx, [rsi+3198h]; this
0x14003391e  call    ?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)
0x140033923  test    eax, eax
0x140033925  jnz     short loc_14003399E
0x140033927  test    dword ptr [rsi+0AB8h], 400h
0x140033931  jnz     short loc_14003399E
0x140033933  mov     rax, cs:KdDebuggerEnabled
0x14003393a  cmp     byte ptr [rax], 0
0x14003393d  jz      short loc_14003399E
0x14003393f  lea     rcx, aErrorSubmittin_2; "Error submitting ColorFill command"
0x140033946  call    cs:__imp_DbgPrint
0x14003394d  nop     dword ptr [rax+rax+00h]
0x140033952  mov     ecx, 2
0x140033957  call    cs:__imp_WdLogSingleEntry0
0x14003395e  nop     dword ptr [rax+rax+00h]
0x140033963  mov     esi, 151h
0x140033968  mov     cs:WdLogGlobalForLineNumber, esi
0x14003396e  call    cs:__imp_WdLogNewEntry5_WdError
0x140033975  nop     dword ptr [rax+rax+00h]
0x14003397a  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140033981  mov     [rax+18h], rcx
0x140033985  mov     ecx, cs:dword_14003E570
0x14003398b  mov     [rax+20h], rcx
0x14003398f  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140033997  mov     cs:WdLogGlobalForLineNumber, esi
0x14003399d  int     3; Trap to Debugger
0x14003399e  lea     rcx, [rsp+58h+var_38]; this
0x1400339a3  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x1400339a8  mov     rax, [rbx+88h]
0x1400339af  xorps   xmm0, xmm0
0x1400339b2  movups  xmmword ptr [rax], xmm0
0x1400339b5  mov     dword ptr [rbx+90h], 0
0x1400339bf  xor     eax, eax
0x1400339c1  movups  xmm0, xmmword ptr [rdi]
0x1400339c4  mov     ecx, eax
0x1400339c6  mov     rax, [rbx+88h]
0x1400339cd  add     rcx, rcx
0x1400339d0  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x1400339d5  inc     dword ptr [rbx+90h]
0x1400339db  add     rsp, 38h
0x1400339df  pop     rdi
0x1400339e0  pop     rsi
0x1400339e1  pop     rbp
0x1400339e2  pop     rbx
0x1400339e3  retn
```
