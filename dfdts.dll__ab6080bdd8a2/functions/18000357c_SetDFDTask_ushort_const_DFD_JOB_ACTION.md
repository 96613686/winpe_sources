# SetDFDTask(ushort const *,DFD_JOB_ACTION)

- ea: `0x18000357c`
- end: `0x18000368e`
- name: `?SetDFDTask@@YAJPEBGW4DFD_JOB_ACTION@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002450`
- `0x180002790`

## callees

- `0x180001064`
- `0x180002c90`
- `0x18000357c`
- `0x180007084`
- `0x1800070d8`
- `0x180007340`
- `0x1800075d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003668`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003668`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800035cd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800035cd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003673`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003673`

## pseudocode

```c
__int64 __fastcall SetDFDTask(const unsigned __int16 *a1, int a2)
{
  char v4; // r14
  LPVOID *v5; // rax
  LPVOID *v6; // rbx
  HRESULT v7; // edi
  int v8; // esi
  int v9; // eax
  bool v10; // r8

  v4 = 0;
  v5 = (LPVOID *)operator new(0x18u);
  v6 = v5;
  if ( v5 )
  {
    v5[2] = 0;
    v5[1] = 0;
    *v5 = 0;
    v7 = CoInitializeEx(0, 0);
    if ( v7 >= 0 )
    {
      v4 = 1;
      v7 = DfdTask::Initialize(v6);
      if ( v7 >= 0 )
      {
        if ( a2 )
        {
          v8 = a2 - 1;
          if ( v8 )
          {
            if ( v8 != 1 )
              goto LABEL_18;
            v9 = DfdTask::RemoveTask((DfdTask *)v6, a1);
LABEL_11:
            v7 = v9;
            if ( v9 < 0 )
              goto LABEL_14;
LABEL_18:
            DfdTask::~DfdTask((DfdTask *)v6);
            operator delete(v6);
            goto LABEL_19;
          }
          v10 = 0;
        }
        else
        {
          v10 = 1;
        }
        v9 = DfdTask::ChangeDFDTaskStatus((DfdTask *)v6, a1, v10);
        goto LABEL_11;
      }
    }
  }
  else
  {
    v6 = 0;
    v7 = -2147024882;
  }
LABEL_14:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids, (unsigned int)v7);
  if ( v6 )
    goto LABEL_18;
LABEL_19:
  if ( v4 )
    CoUninitialize();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000357c  mov     [rsp+arg_0], rbx
0x180003581  mov     [rsp+arg_8], rbp
0x180003586  push    rsi
0x180003587  push    rdi
0x180003588  push    r14
0x18000358a  sub     rsp, 20h
0x18000358e  mov     rbp, rcx
0x180003591  mov     esi, edx
0x180003593  mov     ecx, 18h; Size
0x180003598  xor     r14b, r14b
0x18000359b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800035a0  mov     [rsp+38h+arg_10], rax
0x1800035a5  mov     rbx, rax
0x1800035a8  test    rax, rax
0x1800035ab  jz      short loc_180003620
0x1800035ad  mov     qword ptr [rax+10h], 0
0x1800035b5  mov     qword ptr [rax+8], 0
0x1800035bd  mov     qword ptr [rax], 0
0x1800035c4  test    rax, rax
0x1800035c7  jz      short loc_180003622
0x1800035c9  xor     edx, edx; dwCoInit
0x1800035cb  xor     ecx, ecx; pvReserved
0x1800035cd  call    cs:__imp_CoInitializeEx
0x1800035d3  mov     edi, eax
0x1800035d5  test    eax, eax
0x1800035d7  js      short loc_180003627
0x1800035d9  mov     rcx, rbx; ppv
0x1800035dc  mov     r14b, 1
0x1800035df  call    ?Initialize@DfdTask@@QEAAJXZ; DfdTask::Initialize(void)
0x1800035e4  mov     edi, eax
0x1800035e6  test    eax, eax
0x1800035e8  js      short loc_180003627
0x1800035ea  test    esi, esi
0x1800035ec  jz      short loc_18000360A
0x1800035ee  sub     esi, 1
0x1800035f1  jz      short loc_180003605
0x1800035f3  cmp     esi, 1
0x1800035f6  jnz     short loc_18000365D
0x1800035f8  mov     rdx, rbp; unsigned __int16 *
0x1800035fb  mov     rcx, rbx; this
0x1800035fe  call    ?RemoveTask@DfdTask@@QEAAJPEBG@Z; DfdTask::RemoveTask(ushort const *)
0x180003603  jmp     short loc_180003618
0x180003605  xor     r8d, r8d
0x180003608  jmp     short loc_18000360D
0x18000360a  mov     r8b, r14b; bool
0x18000360d  mov     rdx, rbp; unsigned __int16 *
0x180003610  mov     rcx, rbx; this
0x180003613  call    ?ChangeDFDTaskStatus@DfdTask@@QEAAJPEBG_N@Z; TaskScheduler COM sink toggles fixed task names opened under \Microsoft\Windows\DiskDiagnostic, not caller-controlled XML/action/working directory.
0x180003618  mov     edi, eax
0x18000361a  test    eax, eax
0x18000361c  jns     short loc_18000365D
0x18000361e  jmp     short loc_180003627
0x180003620  xor     ebx, ebx
0x180003622  mov     edi, 8007000Eh
0x180003627  mov     rcx, cs:WPP_GLOBAL_Control
0x18000362e  lea     rax, WPP_GLOBAL_Control
0x180003635  cmp     rcx, rax
0x180003638  jz      short loc_180003658
0x18000363a  test    byte ptr [rcx+1Ch], 1
0x18000363e  jz      short loc_180003658
0x180003640  mov     rcx, [rcx+10h]
0x180003644  lea     r8, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids
0x18000364b  mov     edx, 12h
0x180003650  mov     r9d, edi
0x180003653  call    WPP_SF_d
0x180003658  test    rbx, rbx
0x18000365b  jz      short loc_18000366E
0x18000365d  mov     rcx, rbx; this
0x180003660  call    ??1DfdTask@@QEAA@XZ; DfdTask::~DfdTask(void)
0x180003665  mov     rcx, rbx
0x180003668  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000366e  test    r14b, r14b
0x180003671  jz      short loc_180003679
0x180003673  call    cs:__imp_CoUninitialize
0x180003679  mov     rbx, [rsp+38h+arg_0]
0x18000367e  mov     eax, edi
0x180003680  mov     rbp, [rsp+38h+arg_8]
0x180003685  add     rsp, 20h
0x180003689  pop     r14
0x18000368b  pop     rdi
0x18000368c  pop     rsi
0x18000368d  retn
```
