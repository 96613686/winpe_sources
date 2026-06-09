# UlControlServiceIoctl

- ea: `0x1c01191a0`
- end: `0x1c0119385`
- name: `UlControlServiceIoctl`
- size: `485`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1c0034bc0`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c00a0b70`
- `0x1c00a1218`
- `0x1c00a133c`
- `0x1c01191a0`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1c0119218`
- `ntoskrnl!IoIs32bitProcess` at `0x1c011924d`
- `ntoskrnl!IoIs32bitProcess` at `0x1c011929d`
- `ntoskrnl!IoIs32bitProcess` at `0x1c01192eb`
- `ntoskrnl!IoIs32bitProcess` at `0x1c0119218`
- `ntoskrnl!IoIs32bitProcess` at `0x1c011924d`
- `ntoskrnl!IoIs32bitProcess` at `0x1c011929d`
- `ntoskrnl!IoIs32bitProcess` at `0x1c01192eb`
- `ntoskrnl!IofCompleteRequest` at `0x1c0119342`
- `ntoskrnl!IofCompleteRequest` at `0x1c0119342`

## pseudocode

```c
__int64 __fastcall UlControlServiceIoctl(PIRP Irp, __int64 a2)
{
  unsigned int v2; // ebx
  NTSTATUS CommChannel; // edi
  BOOLEAN v6; // al
  int v7; // edx
  BOOLEAN v8; // al
  __int64 v9; // rax
  NTSTATUS v10; // eax
  __int64 v12; // [rsp+40h] [rbp-30h] BYREF
  __int64 v13; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+50h] [rbp-20h] BYREF
  __int128 v15; // [rsp+58h] [rbp-18h]
  __int64 v16; // [rsp+68h] [rbp-8h]
  int v17; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+40h] BYREF
  int *v19; // [rsp+B8h] [rbp+48h] BYREF

  v2 = 0;
  v14 = 0;
  v16 = 0;
  v13 = 0;
  v12 = 0;
  v17 = 0;
  LODWORD(v18) = 0;
  v19 = 0;
  v15 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qq(113, WPP_18ca8755388c316524f95a91261e2540_Traceguids, Irp, a2);
  CommChannel = UlGetCommChannel(a2, &v14);
  if ( CommChannel >= 0 )
  {
    v6 = IoIs32bitProcess(Irp);
    CommChannel = UxGetInputBuffer(Irp, a2, v6 != 0 ? 12 : 24, &v19);
    if ( CommChannel >= 0 )
    {
      if ( IoIs32bitProcess(Irp) )
      {
        v7 = *v19;
        *((_QWORD *)&v15 + 1) = (unsigned int)v19[1];
        LODWORD(v16) = v19[2];
        LODWORD(v15) = v7;
      }
      else
      {
        v7 = *v19;
      }
      if ( (unsigned int)v7 < 2 )
      {
        v8 = IoIs32bitProcess(Irp);
        CommChannel = UxGetOutputBufferForOutDirect(
                        (_DWORD)Irp,
                        a2,
                        16,
                        v8 != 0 ? 4 : 8,
                        (__int64)&v13,
                        (__int64)&v12,
                        (__int64)&v17);
        if ( CommChannel < 0 )
          goto LABEL_18;
        if ( IoIs32bitProcess(Irp) )
        {
          v9 = v12;
          if ( (v12 & 7) != 0 )
          {
            CommChannel = -1073741115;
            goto LABEL_18;
          }
          goto LABEL_17;
        }
      }
      else if ( v7 <= 1 || v7 > 4 )
      {
        CommChannel = -1073741811;
        goto LABEL_18;
      }
      v9 = v12;
LABEL_17:
      v10 = UlControlService(Irp, v9, (__int64)&v18);
      v2 = v18;
      CommChannel = v10;
    }
  }
LABEL_18:
  Irp->IoStatus.Information = v2;
  Irp->IoStatus.Status = CommChannel;
  IofCompleteRequest(Irp, 0);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_D(114, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
  return (unsigned int)CommChannel;
}

```

## disassembly

```asm
0x1c01191a0  mov     [rsp-28h+arg_8], rbx
0x1c01191a5  push    rbp
0x1c01191a6  push    rsi
0x1c01191a7  push    rdi
0x1c01191a8  push    r14
0x1c01191aa  push    r15
0x1c01191ac  mov     rbp, rsp
0x1c01191af  sub     rsp, 70h
0x1c01191b3  xor     ebx, ebx
0x1c01191b5  xorps   xmm0, xmm0
0x1c01191b8  xor     eax, eax
0x1c01191ba  mov     [rbp+var_20], rbx
0x1c01191be  mov     [rbp+var_8], rax
0x1c01191c2  mov     r14, rdx
0x1c01191c5  mov     rsi, rcx
0x1c01191c8  mov     [rbp+var_28], rbx
0x1c01191cc  mov     [rbp+var_30], rbx
0x1c01191d0  mov     [rbp+arg_0], ebx
0x1c01191d3  mov     dword ptr [rbp+arg_10], ebx
0x1c01191d6  mov     [rbp+arg_18], rbx
0x1c01191da  movups  [rbp+var_18], xmm0
0x1c01191de  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c01191e8  jz      short loc_1C01191FF
0x1c01191ea  mov     r9, rdx
0x1c01191ed  lea     ecx, [rbx+71h]
0x1c01191f0  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c01191f7  mov     r8, rsi
0x1c01191fa  call    WPP_SF_qq
0x1c01191ff  lea     rdx, [rbp+var_20]
0x1c0119203  mov     rcx, r14
0x1c0119206  call    UlGetCommChannel
0x1c011920b  mov     edi, eax
0x1c011920d  test    eax, eax
0x1c011920f  js      loc_1C0119334
0x1c0119215  mov     rcx, rsi; Irp
0x1c0119218  call    cs:__imp_IoIs32bitProcess
0x1c011921f  nop     dword ptr [rax+rax+00h]
0x1c0119224  lea     r9, [rbp+arg_18]
0x1c0119228  mov     rdx, r14
0x1c011922b  neg     al
0x1c011922d  mov     rcx, rsi
0x1c0119230  sbb     r8d, r8d
0x1c0119233  and     r8d, 0FFFFFFF4h
0x1c0119237  add     r8d, 18h
0x1c011923b  call    UxGetInputBuffer
0x1c0119240  mov     edi, eax
0x1c0119242  test    eax, eax
0x1c0119244  js      loc_1C0119334
0x1c011924a  mov     rcx, rsi; Irp
0x1c011924d  call    cs:__imp_IoIs32bitProcess
0x1c0119254  nop     dword ptr [rax+rax+00h]
0x1c0119259  test    al, al
0x1c011925b  jz      short loc_1C0119279
0x1c011925d  mov     rcx, [rbp+arg_18]
0x1c0119261  lea     r15, [rbp+var_18]
0x1c0119265  mov     eax, [rcx+4]
0x1c0119268  mov     edx, [rcx]
0x1c011926a  mov     qword ptr [rbp+var_18+8], rax
0x1c011926e  mov     eax, [rcx+8]
0x1c0119271  mov     dword ptr [rbp+var_8], eax
0x1c0119274  mov     dword ptr [rbp+var_18], edx
0x1c0119277  jmp     short loc_1C0119280
0x1c0119279  mov     r15, [rbp+arg_18]
0x1c011927d  mov     edx, [r15]
0x1c0119280  test    edx, edx
0x1c0119282  jz      short loc_1C011929A
0x1c0119284  cmp     edx, 1
0x1c0119287  jz      short loc_1C011929A
0x1c0119289  jle     short loc_1C0119290
0x1c011928b  cmp     edx, 4
0x1c011928e  jle     short loc_1C011930A
0x1c0119290  mov     edi, 0C000000Dh
0x1c0119295  jmp     loc_1C0119334
0x1c011929a  mov     rcx, rsi; Irp
0x1c011929d  call    cs:__imp_IoIs32bitProcess
0x1c01192a4  nop     dword ptr [rax+rax+00h]
0x1c01192a9  mov     r8d, 10h
0x1c01192af  mov     rdx, r14
0x1c01192b2  neg     al
0x1c01192b4  mov     rcx, rsi
0x1c01192b7  lea     rax, [rbp+arg_0]
0x1c01192bb  mov     [rsp+70h+var_40], rax
0x1c01192c0  sbb     r9, r9
0x1c01192c3  lea     rax, [rbp+var_30]
0x1c01192c7  and     r9, 0FFFFFFFFFFFFFFFCh
0x1c01192cb  mov     [rsp+70h+var_48], rax
0x1c01192d0  add     r9, 8
0x1c01192d4  lea     rax, [rbp+var_28]
0x1c01192d8  mov     [rsp+70h+var_50], rax
0x1c01192dd  call    UxGetOutputBufferForOutDirect
0x1c01192e2  mov     edi, eax
0x1c01192e4  test    eax, eax
0x1c01192e6  js      short loc_1C0119334
0x1c01192e8  mov     rcx, rsi; Irp
0x1c01192eb  call    cs:__imp_IoIs32bitProcess
0x1c01192f2  nop     dword ptr [rax+rax+00h]
0x1c01192f7  test    al, al
0x1c01192f9  jz      short loc_1C011930A
0x1c01192fb  mov     rax, [rbp+var_30]
0x1c01192ff  test    al, 7
0x1c0119301  jz      short loc_1C011930E
0x1c0119303  mov     edi, 0C00002C5h
0x1c0119308  jmp     short loc_1C0119334
0x1c011930a  mov     rax, [rbp+var_30]
0x1c011930e  mov     r9d, [rbp+arg_0]
0x1c0119312  lea     rcx, [rbp+arg_10]
0x1c0119316  mov     r8, [rbp+var_28]
0x1c011931a  mov     rdx, r15
0x1c011931d  mov     [rsp+70h+var_48], rcx; __int64
0x1c0119322  mov     rcx, rsi; Irp
0x1c0119325  mov     [rsp+70h+var_50], rax; __int64
0x1c011932a  call    UlControlService
0x1c011932f  mov     ebx, dword ptr [rbp+arg_10]
0x1c0119332  mov     edi, eax
0x1c0119334  mov     eax, ebx
0x1c0119336  xor     edx, edx; PriorityBoost
0x1c0119338  mov     rcx, rsi; Irp
0x1c011933b  mov     [rsi+38h], rax
0x1c011933f  mov     [rsi+30h], edi
0x1c0119342  call    cs:__imp_IofCompleteRequest
0x1c0119349  nop     dword ptr [rax+rax+00h]
0x1c011934e  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c0119358  jz      short loc_1C011936E
0x1c011935a  mov     ecx, 72h ; 'r'
0x1c011935f  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c0119366  mov     r8d, edi
0x1c0119369  call    WPP_SF_D
0x1c011936e  mov     rbx, [rsp+70h+arg_8]
0x1c0119376  mov     eax, edi
0x1c0119378  add     rsp, 70h
0x1c011937c  pop     r15
0x1c011937e  pop     r14
0x1c0119380  pop     rdi
0x1c0119381  pop     rsi
0x1c0119382  pop     rbp
0x1c0119383  retn
```
