# Smb2TreeConnect_Receive

- ea: `0x140029250`
- end: `0x140029661`
- name: `Smb2TreeConnect_Receive`
- size: `1041`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x14000b9c0`
- `0x14000fa00`
- `0x140015570`
- `0x140029084`
- `0x1400290f8`
- `0x140029250`
- `0x140029668`
- `0x1400297fc`
- `0x140029840`

## import_xrefs

- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002963d`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002963d`
- `mrxsmb!SmbCeContinueExchange` at `0x140029502`
- `mrxsmb!SmbCeContinueExchange` at `0x140029502`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x1400294d4`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x1400294d4`

## pseudocode

```c
__int64 __fastcall Smb2TreeConnect_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7)
{
  int v7; // ebx
  unsigned int v8; // r15d
  int v9; // ebp
  __int64 v12; // rdi
  __int64 v13; // r9
  __int64 v14; // r10
  int v15; // eax
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned int v19; // esi
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rcx
  char v23; // al
  unsigned __int64 v25; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int16 *v26; // [rsp+88h] [rbp+10h] BYREF

  v7 = *(_DWORD *)(a3 + 16);
  v8 = 0;
  v9 = 0;
  v12 = a1;
  if ( a2 == a1 + 1032 )
  {
    v13 = *(_QWORD *)(a1 + 88);
    v14 = *(_QWORD *)(v13 + 424);
    if ( v7 )
    {
      switch ( v7 )
      {
        case -1073741629:
          if ( *(_DWORD *)(a3 + 20) == -1067646975 )
          {
            v7 = -1067646975;
            *(_DWORD *)(a3 + 16) = -1067646975;
LABEL_10:
            v26 = 0;
            LODWORD(v25) = 0;
            v15 = Smb2QueryErrorDataFromResponse(a7 + 64, a4, 0, &v26, (unsigned int *)&v25);
            v8 = v15;
            if ( v15 < 0 )
            {
              v7 = v15;
              goto LABEL_59;
            }
            if ( (_DWORD)v25 == 2 )
            {
              v16 = *v26;
              *(_WORD *)(v12 + 1024) = v16;
              LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  10,
                  WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids,
                  v12,
                  v16);
              }
            }
            else
            {
              LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids, v12);
              }
              v7 = -1073741629;
            }
          }
          break;
        case -1073741790:
          if ( (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 1) != 0 )
            McTemplateK0qqhzr2hzr4_EtwWriteTransfer(
              *(_WORD *)(v14 + 96) >> 1,
              (unsigned int)TreeConnectFailure,
              a3,
              12,
              34,
              *(_WORD *)(v14 + 96) >> 1,
              *(_QWORD *)(v14 + 104),
              0,
              0);
          break;
        case -1067646975:
          goto LABEL_10;
        default:
          if ( v7 == -1073741620 && *(_BYTE *)(a1 + 3808) && a5 > 0x50 )
            v8 = Smb2BufferErrorResponse(a2, a7, a4, a5, a6);
          break;
      }
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(a1, (unsigned int)TreeConnectError, v12 + 312, v7, 112, 11);
      v9 = 12;
      goto LABEL_59;
    }
    if ( a4 >= 0x50 && (v17 = a7, *(_WORD *)(a7 + 64) == 16) )
    {
      *(_DWORD *)(v13 + 436) = *(_DWORD *)(a7 + 36);
      *(_DWORD *)(v13 + 440) = *(_DWORD *)(v17 + 76);
      *(_DWORD *)(v13 + 444) = 0;
      *(_OWORD *)(v12 + 3810) = *(_OWORD *)(v17 + 64);
      if ( !(unsigned __int8)SmbCeCheckServerEntryDialect(*(_QWORD *)(v14 + 88), 3, 1, 1) )
      {
        v18 = *(_QWORD *)(v12 + 80);
        if ( v18 )
        {
          if ( (*(_BYTE *)(v18 + 4) & 3) == 0 )
            SmbCeContinueExchange(v12);
        }
      }
    }
    else
    {
      v7 = -1073741629;
    }
  }
  else if ( a2 == a1 + 2416 )
  {
    if ( v7 >= 0 )
    {
      v19 = a5;
      if ( a5 >= 0x88
        && (v20 = a7, *(_WORD *)(a7 + 64) == 49)
        && (v21 = *(_DWORD *)(a7 + 100), v21 <= *(_DWORD *)(a2 + 744))
        && (v22 = *(unsigned int *)(a7 + 96), (unsigned int)v22 <= a5)
        && v21 <= a5
        && (unsigned int)v22 + v21 <= a5 )
      {
        if ( v21 && (unsigned int)v22 + v21 > a4 )
        {
          *(_DWORD *)(a2 + 748) = v21;
          v8 = -1073741802;
          *a6 = *(_DWORD *)(v20 + 96);
          goto LABEL_59;
        }
        v23 = Smb2ValidateNegotiateInfo(a7 + v22, *(_QWORD *)(v12 + 72));
        *a6 = v19;
        if ( v23 )
          goto LABEL_59;
      }
      else
      {
        v7 = -1073741629;
        *a6 = a5;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids,
          *(_QWORD *)(v12 + 72));
      }
      Smb2ProcessNegotiateValidationFailure(v12);
      v9 = 13;
    }
    else
    {
      if ( v7 != -1073741790 && v7 != -1073700864 )
        v7 = 0;
      *a6 = a5;
    }
  }
LABEL_59:
  v25 = __PAIR64__(v9, v7);
  SmbCseUpdateBufferContextStatus(a2, __PAIR64__(v9, v7));
  return v8;
}

```

## disassembly

```asm
0x140029250  mov     [rsp+arg_10], rbx
0x140029255  push    rbp
0x140029256  push    rsi
0x140029257  push    rdi
0x140029258  push    r14
0x14002925a  push    r15
0x14002925c  sub     rsp, 50h
0x140029260  mov     ebx, [r8+10h]
0x140029264  lea     rax, [rcx+408h]
0x14002926b  xor     r15d, r15d
0x14002926e  xor     ebp, ebp
0x140029270  mov     r11d, r9d
0x140029273  mov     r14, rdx
0x140029276  mov     rdi, rcx
0x140029279  cmp     rdx, rax
0x14002927c  jnz     loc_140029513
0x140029282  mov     r9, [rcx+58h]
0x140029286  mov     r10, [r9+1A8h]
0x14002928d  test    ebx, ebx
0x14002928f  jz      loc_14002947E
0x140029295  lea     esi, [rbp+0Bh]
0x140029298  cmp     ebx, 0C00000C3h
0x14002929e  jnz     short loc_1400292B7
0x1400292a0  mov     eax, 0C05D0001h
0x1400292a5  cmp     [r8+14h], eax
0x1400292a9  jnz     loc_140029449
0x1400292af  mov     ebx, eax
0x1400292b1  mov     [r8+10h], eax
0x1400292b5  jmp     short loc_14002931A
0x1400292b7  cmp     ebx, 0C0000022h
0x1400292bd  jnz     short loc_14002930D
0x1400292bf  test    byte ptr cs:WPP_MAIN_CB.Queue+14h, 1
0x1400292c6  jz      loc_140029449
0x1400292cc  movzx   ecx, word ptr [r10+60h]
0x1400292d1  lea     rdx, TreeConnectFailure
0x1400292d8  xor     eax, eax
0x1400292da  shr     cx, 1
0x1400292dd  mov     [rsp+78h+var_38], rax
0x1400292e2  mov     r9d, 0Ch
0x1400292e8  mov     [rsp+78h+var_40], ax
0x1400292ed  mov     rax, [r10+68h]
0x1400292f1  mov     [rsp+78h+var_48], rax
0x1400292f6  mov     word ptr [rsp+78h+var_50], cx
0x1400292fb  mov     dword ptr [rsp+78h+var_58], 0C0000022h
0x140029303  call    McTemplateK0qqhzr2hzr4_EtwWriteTransfer
0x140029308  jmp     loc_140029449
0x14002930d  mov     eax, 0C05D0001h
0x140029312  cmp     ebx, eax
0x140029314  jnz     loc_140029407
0x14002931a  mov     rcx, [rsp+78h+arg_30]
0x140029322  lea     rax, [rsp+78h+arg_0]
0x14002932a  add     rcx, 40h ; '@'
0x14002932e  mov     [rsp+78h+arg_8], rbp
0x140029336  lea     r9, [rsp+78h+arg_8]
0x14002933e  mov     dword ptr [rsp+78h+arg_0], ebp
0x140029345  xor     r8d, r8d
0x140029348  mov     [rsp+78h+var_58], rax
0x14002934d  mov     edx, r11d
0x140029350  call    Smb2QueryErrorDataFromResponse
0x140029355  mov     r15d, eax
0x140029358  test    eax, eax
0x14002935a  jns     short loc_140029363
0x14002935c  mov     ebx, eax
0x14002935e  jmp     loc_140029624
0x140029363  cmp     dword ptr [rsp+78h+arg_0], 2
0x14002936b  jnz     short loc_1400293CB
0x14002936d  mov     rax, [rsp+78h+arg_8]
0x140029375  movzx   edx, word ptr [rax]
0x140029378  mov     [rdi+400h], dx
0x14002937f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029386  lea     rax, WPP_GLOBAL_Control
0x14002938d  cmp     rcx, rax
0x140029390  jz      loc_140029449
0x140029396  mov     eax, [rcx+2Ch]
0x140029399  test    al, 1
0x14002939b  jz      loc_140029449
0x1400293a1  cmp     byte ptr [rcx+29h], 1
0x1400293a5  jb      loc_140029449
0x1400293ab  mov     rcx, [rcx+18h]
0x1400293af  lea     r8, WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids
0x1400293b6  mov     eax, edx
0x1400293b8  mov     r9, rdi
0x1400293bb  mov     edx, 0Ah
0x1400293c0  mov     dword ptr [rsp+78h+var_58], eax
0x1400293c4  call    WPP_SF_qD
0x1400293c9  jmp     short loc_140029449
0x1400293cb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400293d2  lea     rax, WPP_GLOBAL_Control
0x1400293d9  cmp     rcx, rax
0x1400293dc  jz      short loc_140029400
0x1400293de  mov     eax, [rcx+2Ch]
0x1400293e1  test    al, 1
0x1400293e3  jz      short loc_140029400
0x1400293e5  cmp     byte ptr [rcx+29h], 1
0x1400293e9  jb      short loc_140029400
0x1400293eb  mov     rcx, [rcx+18h]
0x1400293ef  lea     r8, WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids
0x1400293f6  mov     edx, esi
0x1400293f8  mov     r9, rdi
0x1400293fb  call    WPP_SF_q
0x140029400  mov     ebx, 0C00000C3h
0x140029405  jmp     short loc_140029449
0x140029407  cmp     ebx, 0C00000CCh
0x14002940d  jnz     short loc_140029449
0x14002940f  cmp     [rcx+0EE0h], bpl
0x140029416  jz      short loc_140029449
0x140029418  mov     r9d, [rsp+78h+arg_20]
0x140029420  cmp     r9d, 50h ; 'P'
0x140029424  jbe     short loc_140029449
0x140029426  mov     rax, [rsp+78h+arg_28]
0x14002942e  mov     r8d, r11d
0x140029431  mov     rdx, [rsp+78h+arg_30]
0x140029439  mov     rcx, r14
0x14002943c  mov     [rsp+78h+var_58], rax
0x140029441  call    Smb2BufferErrorResponse
0x140029446  mov     r15d, eax
0x140029449  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 1
0x140029450  jz      short loc_140029474
0x140029452  lea     r8, [rdi+138h]
0x140029459  mov     [rsp+78h+var_50], esi
0x14002945d  mov     r9d, ebx
0x140029460  mov     dword ptr [rsp+78h+var_58], 20300170h
0x140029468  lea     rdx, TreeConnectError
0x14002946f  call    McTemplateK0qqq_EtwWriteTransfer
0x140029474  mov     ebp, 0Ch
0x140029479  jmp     loc_140029624
0x14002947e  cmp     r11d, 50h ; 'P'
0x140029482  jnb     short loc_14002948E
0x140029484  mov     ebx, 0C00000C3h
0x140029489  jmp     loc_140029624
0x14002948e  mov     rcx, [rsp+78h+arg_30]
0x140029496  cmp     word ptr [rcx+40h], 10h
0x14002949b  jnz     short loc_140029484
0x14002949d  mov     eax, [rcx+24h]
0x1400294a0  mov     edx, 3
0x1400294a5  mov     [r9+1B4h], eax
0x1400294ac  mov     eax, [rcx+4Ch]
0x1400294af  mov     [r9+1B8h], eax
0x1400294b6  mov     [r9+1BCh], ebp
0x1400294bd  lea     r9d, [rdx-2]
0x1400294c1  movups  xmm0, xmmword ptr [rcx+40h]
0x1400294c5  mov     r8d, r9d
0x1400294c8  movdqu  xmmword ptr [rdi+0EE2h], xmm0
0x1400294d0  mov     rcx, [r10+58h]
0x1400294d4  call    cs:__imp_SmbCeCheckServerEntryDialect
0x1400294db  nop     dword ptr [rax+rax+00h]
0x1400294e0  test    al, al
0x1400294e2  jnz     loc_140029624
0x1400294e8  mov     rax, [rdi+50h]
0x1400294ec  test    rax, rax
0x1400294ef  jz      loc_140029624
0x1400294f5  test    byte ptr [rax+4], 3
0x1400294f9  jnz     loc_140029624
0x1400294ff  mov     rcx, rdi
0x140029502  call    cs:__imp_SmbCeContinueExchange
0x140029509  nop     dword ptr [rax+rax+00h]
0x14002950e  jmp     loc_140029624
0x140029513  lea     rax, [rcx+970h]
0x14002951a  cmp     r14, rax
0x14002951d  jnz     loc_140029624
0x140029523  test    ebx, ebx
0x140029525  jns     short loc_140029550
0x140029527  cmp     ebx, 0C0000022h
0x14002952d  jz      short loc_14002953A
0x14002952f  xor     eax, eax
0x140029531  cmp     ebx, 0C000A000h
0x140029537  cmovnz  ebx, eax
0x14002953a  mov     rcx, [rsp+78h+arg_28]
0x140029542  mov     eax, [rsp+78h+arg_20]
0x140029549  mov     [rcx], eax
0x14002954b  jmp     loc_140029624
0x140029550  mov     esi, [rsp+78h+arg_20]
0x140029557  cmp     esi, 88h
0x14002955d  jb      short loc_1400295CF
0x14002955f  mov     rdx, [rsp+78h+arg_30]
0x140029567  cmp     word ptr [rdx+40h], 31h ; '1'
0x14002956c  jnz     short loc_1400295CF
0x14002956e  mov     eax, [rdx+64h]
0x140029571  cmp     eax, [r14+2E8h]
0x140029578  ja      short loc_1400295CF
0x14002957a  mov     ecx, [rdx+60h]
0x14002957d  cmp     ecx, esi
0x14002957f  ja      short loc_1400295CF
0x140029581  cmp     eax, esi
0x140029583  ja      short loc_1400295CF
0x140029585  lea     r8d, [rcx+rax]
0x140029589  cmp     r8d, esi
0x14002958c  ja      short loc_1400295CF
0x14002958e  test    eax, eax
0x140029590  jz      short loc_1400295B3
0x140029592  cmp     r8d, r11d
0x140029595  jbe     short loc_1400295B3
0x140029597  mov     [r14+2ECh], eax
0x14002959e  mov     r15d, 0C0000016h
0x1400295a4  mov     rax, [rsp+78h+arg_28]
0x1400295ac  mov     ecx, [rdx+60h]
0x1400295af  mov     [rax], ecx
0x1400295b1  jmp     short loc_140029624
0x1400295b3  add     rcx, rdx
0x1400295b6  mov     rdx, [rdi+48h]
0x1400295ba  call    Smb2ValidateNegotiateInfo
0x1400295bf  mov     rcx, [rsp+78h+arg_28]
0x1400295c7  mov     [rcx], esi
0x1400295c9  test    al, al
0x1400295cb  jnz     short loc_140029624
0x1400295cd  jmp     short loc_1400295DE
0x1400295cf  mov     rax, [rsp+78h+arg_28]
0x1400295d7  mov     ebx, 0C00000C3h
0x1400295dc  mov     [rax], esi
0x1400295de  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400295e5  lea     rax, WPP_GLOBAL_Control
0x1400295ec  cmp     rcx, rax
0x1400295ef  jz      short loc_140029617
0x1400295f1  mov     eax, [rcx+2Ch]
0x1400295f4  test    al, 1
0x1400295f6  jz      short loc_140029617
0x1400295f8  cmp     byte ptr [rcx+29h], 1
0x1400295fc  jb      short loc_140029617
0x1400295fe  mov     r9, [rdi+48h]
0x140029602  lea     r8, WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids
0x140029609  mov     rcx, [rcx+18h]
0x14002960d  mov     edx, 0Ch
0x140029612  call    WPP_SF_q
0x140029617  mov     rcx, rdi
0x14002961a  call    Smb2ProcessNegotiateValidationFailure
0x14002961f  mov     ebp, 0Dh
0x140029624  mov     dword ptr [rsp+78h+arg_0], ebx
0x14002962b  mov     rcx, r14
0x14002962e  mov     dword ptr [rsp+78h+arg_0+4], ebp
0x140029635  mov     rdx, [rsp+78h+arg_0]
0x14002963d  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x140029644  nop     dword ptr [rax+rax+00h]
0x140029649  mov     rbx, [rsp+78h+arg_10]
0x140029651  mov     eax, r15d
0x140029654  add     rsp, 50h
0x140029658  pop     r15
0x14002965a  pop     r14
0x14002965c  pop     rdi
0x14002965d  pop     rsi
0x14002965e  pop     rbp
0x14002965f  retn
```
