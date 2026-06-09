# MsQuicGetParam

- ea: `0x140023350`
- end: `0x1400235b6`
- name: `MsQuicGetParam`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14000c4b8`
- `0x140023350`
- `0x1400235bc`
- `0x14002b6f4`
- `0x1400337e4`
- `0x14003eb54`
- `0x14003eca4`
- `0x14003ef44`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400234b3`
- `ntoskrnl!KeInitializeEvent` at `0x1400234b3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002345e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002345e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002351d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002351d`

## pseudocode

```c
__int64 __fastcall MsQuicGetParam(unsigned int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // esi
  int v5; // r15d
  int v6; // ebx
  unsigned int GlobalParam; // eax
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int *v13; // rbx
  __int64 v14; // rcx
  char v15; // r15
  __int128 v17; // [rsp+30h] [rbp-59h] BYREF
  __int128 v18; // [rsp+40h] [rbp-49h]
  __int128 v19; // [rsp+50h] [rbp-39h]
  __int64 v20; // [rsp+60h] [rbp-29h]
  struct _KEVENT Event; // [rsp+68h] [rbp-21h] BYREF
  __int128 v22; // [rsp+80h] [rbp-9h] BYREF
  __int64 v23; // [rsp+90h] [rbp+7h]
  __int128 *v24; // [rsp+98h] [rbp+Fh]
  __int128 v25; // [rsp+A0h] [rbp+17h]
  __int64 v26; // [rsp+B0h] [rbp+27h]
  unsigned int Param; // [rsp+F8h] [rbp+6Fh] BYREF

  v4 = a2 & 0xBFFFFFFF;
  v5 = a2 & 0x40000000;
  v6 = a2 & 0x3F000000;
  if ( (a1 == 0) != ((a2 & 0x3F000000) == 0x1000000) || !a3 )
    return 3221225485LL;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 1, a1);
  Param = 0;
  if ( v6 == 0x1000000 )
  {
    GlobalParam = QuicLibraryGetGlobalParam(v4, a3, a4);
LABEL_29:
    Param = GlobalParam;
    goto LABEL_30;
  }
  v12 = *a1;
  if ( *a1 <= 2 )
  {
    GlobalParam = QuicLibraryGetParam(a1, v4, a3, a4);
    goto LABEL_29;
  }
  v11 = 0;
  memset(&Event, 0, sizeof(Event));
  if ( v12 == 5 )
  {
    v13 = (unsigned int *)*((_QWORD *)a1 + 9);
    goto LABEL_13;
  }
  if ( v12 - 3 <= 1 )
  {
    v13 = a1;
LABEL_13:
    if ( (v13[63] & 0x40) != 0 && (*((_BYTE *)v13 + 249) & 4) != 0 )
    {
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1743, "!Connection->State.Freed");
      __int2c();
    }
    if ( (MsQuicLib & 4) != 0 || *((HANDLE *)v13 + 32) == PsGetCurrentThreadId() )
    {
      v15 = *((_BYTE *)v13 + 251) & 0x20;
      if ( !v15 )
        *((_BYTE *)v13 + 251) |= 0x20u;
      Param = QuicLibraryGetParam(a1, v4, a3, a4);
      if ( !v15 )
        *((_BYTE *)v13 + 251) &= ~0x20u;
    }
    else
    {
      v26 = 0;
      LODWORD(v20) = 0;
      v23 = 0;
      v24 = &v17;
      v17 = 0;
      LODWORD(v17) = 12;
      v22 = 0;
      v25 = 0;
      v18 = 0;
      v19 = 0;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      *((_QWORD *)&v18 + 1) = a1;
      *(_QWORD *)&v18 = &Event;
      *((_QWORD *)&v17 + 1) = &Param;
      LODWORD(v19) = v4;
      *((_QWORD *)&v19 + 1) = a3;
      v20 = a4;
      if ( v5 )
        QuicConnQueuePriorityOper(v13, &v22);
      else
        QuicConnQueueOper(v13, &v22);
      if ( (Microsoft_QuicEnableBits & 8) != 0 )
        McTemplateU0_EtwWriteTransfer(v14, QuicApiWaitOperation);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    }
    goto LABEL_30;
  }
  Param = -1073741811;
LABEL_30:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(v11, QuicApiExitStatus, Param);
  return Param;
}

```

## disassembly

```asm
0x140023350  mov     [rsp-8+arg_0], rbx
0x140023355  mov     [rsp-8+arg_10], rsi
0x14002335a  push    rbp
0x14002335b  push    rdi
0x14002335c  push    r12
0x14002335e  push    r14
0x140023360  push    r15
0x140023362  lea     rbp, [rsp-37h]
0x140023367  sub     rsp, 0C0h
0x14002336e  xor     r10d, r10d
0x140023371  mov     esi, edx
0x140023373  btr     esi, 1Eh
0x140023377  mov     r15d, edx
0x14002337a  and     r15d, 40000000h
0x140023381  mov     ebx, esi
0x140023383  and     ebx, 3F000000h
0x140023389  mov     r12, r9
0x14002338c  cmp     ebx, 1000000h
0x140023392  mov     r14, r8
0x140023395  mov     rdi, rcx
0x140023398  setz    r10b
0x14002339c  xor     eax, eax
0x14002339e  test    rcx, rcx
0x1400233a1  setz    al
0x1400233a4  cmp     eax, r10d
0x1400233a7  jnz     loc_140023594
0x1400233ad  test    r8, r8
0x1400233b0  jz      loc_140023594
0x1400233b6  test    cs:Microsoft_QuicEnableBits, 8
0x1400233bd  jz      short loc_1400233CD
0x1400233bf  mov     r9, rcx
0x1400233c2  mov     r8d, 1
0x1400233c8  call    McTemplateU0qp_EtwWriteTransfer
0x1400233cd  and     [rbp+57h+arg_8], 0
0x1400233d1  cmp     ebx, 1000000h
0x1400233d7  jnz     short loc_1400233EB
0x1400233d9  mov     r8, r12
0x1400233dc  mov     rdx, r14
0x1400233df  mov     ecx, esi
0x1400233e1  call    QuicLibraryGetGlobalParam
0x1400233e6  jmp     loc_140023573
0x1400233eb  mov     eax, [rdi]
0x1400233ed  cmp     eax, 2
0x1400233f0  jbe     loc_140023563
0x1400233f6  xor     ecx, ecx
0x1400233f8  xorps   xmm0, xmm0
0x1400233fb  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rcx
0x1400233ff  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x140023403  cmp     eax, 5
0x140023406  jnz     short loc_14002340E
0x140023408  mov     rbx, [rdi+48h]
0x14002340c  jmp     short loc_140023425
0x14002340e  add     eax, 0FFFFFFFDh
0x140023411  cmp     eax, 1
0x140023414  jbe     short loc_140023422
0x140023416  mov     [rbp+57h+arg_8], 0C000000Dh
0x14002341d  jmp     loc_140023576
0x140023422  mov     rbx, rdi
0x140023425  test    byte ptr [rbx+0FCh], 40h
0x14002342c  jz      short loc_140023451
0x14002342e  test    byte ptr [rbx+0F9h], 4
0x140023435  jz      short loc_140023451
0x140023437  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x14002343e  mov     edx, 6CFh
0x140023443  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14002344a  call    CxPlatLogAssert
0x14002344f  int     2Ch; Windows NT - assertion failure
0x140023451  test    cs:MsQuicLib, 4
0x140023458  jnz     loc_14002352B
0x14002345e  call    cs:__imp_PsGetCurrentThreadId
0x140023465  nop     dword ptr [rax+rax+00h]
0x14002346a  cmp     [rbx+100h], rax
0x140023471  jz      loc_14002352B
0x140023477  xorps   xmm0, xmm0
0x14002347a  lea     rcx, [rbp+57h+Event]; Event
0x14002347e  xor     eax, eax
0x140023480  xor     r8d, r8d; State
0x140023483  mov     [rbp+57h+var_30], rax
0x140023487  xor     edx, edx; Type
0x140023489  mov     dword ptr [rbp+57h+var_80], eax
0x14002348c  lea     rax, [rbp+57h+var_B0]
0x140023490  movups  [rbp+57h+var_50], xmm0
0x140023494  mov     qword ptr [rbp+57h+var_50+8], rax
0x140023498  movups  [rbp+57h+var_B0], xmm0
0x14002349c  mov     dword ptr [rbp+57h+var_B0], 0Ch
0x1400234a3  movups  [rbp+57h+var_60], xmm0
0x1400234a7  movups  [rbp+57h+var_40], xmm0
0x1400234ab  movups  [rbp+57h+var_A0], xmm0
0x1400234af  movups  [rbp+57h+var_90], xmm0
0x1400234b3  call    cs:__imp_KeInitializeEvent
0x1400234ba  nop     dword ptr [rax+rax+00h]
0x1400234bf  mov     qword ptr [rbp+57h+var_A0+8], rdi
0x1400234c3  lea     rax, [rbp+57h+Event]
0x1400234c7  mov     qword ptr [rbp+57h+var_A0], rax
0x1400234cb  lea     rax, [rbp+57h+arg_8]
0x1400234cf  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1400234d3  lea     rdx, [rbp+57h+var_60]
0x1400234d7  mov     dword ptr [rbp+57h+var_90], esi
0x1400234da  mov     rcx, rbx
0x1400234dd  mov     qword ptr [rbp+57h+var_90+8], r14
0x1400234e1  mov     [rbp+57h+var_80], r12
0x1400234e5  test    r15d, r15d
0x1400234e8  jz      short loc_1400234F1
0x1400234ea  call    QuicConnQueuePriorityOper
0x1400234ef  jmp     short loc_1400234F6
0x1400234f1  call    QuicConnQueueOper
0x1400234f6  test    cs:Microsoft_QuicEnableBits, 8
0x1400234fd  jz      short loc_14002350B
0x1400234ff  lea     rdx, QuicApiWaitOperation
0x140023506  call    McTemplateU0_EtwWriteTransfer
0x14002350b  and     [rsp+0E0h+var_C0], 0
0x140023511  lea     rcx, [rbp+57h+Event]; Object
0x140023515  xor     r9d, r9d; Alertable
0x140023518  xor     r8d, r8d; WaitMode
0x14002351b  xor     edx, edx; WaitReason
0x14002351d  call    cs:__imp_KeWaitForSingleObject
0x140023524  nop     dword ptr [rax+rax+00h]
0x140023529  jmp     short loc_140023576
0x14002352b  mov     al, [rbx+0FBh]
0x140023531  mov     r15b, al
0x140023534  and     r15b, 20h
0x140023538  jnz     short loc_140023542
0x14002353a  or      al, 20h
0x14002353c  mov     [rbx+0FBh], al
0x140023542  mov     r9, r12
0x140023545  mov     r8, r14
0x140023548  mov     edx, esi
0x14002354a  mov     rcx, rdi
0x14002354d  call    QuicLibraryGetParam
0x140023552  mov     [rbp+57h+arg_8], eax
0x140023555  test    r15b, r15b
0x140023558  jnz     short loc_140023576
0x14002355a  and     byte ptr [rbx+0FBh], 0DFh
0x140023561  jmp     short loc_140023576
0x140023563  mov     r9, r12
0x140023566  mov     r8, r14
0x140023569  mov     edx, esi
0x14002356b  mov     rcx, rdi
0x14002356e  call    QuicLibraryGetParam
0x140023573  mov     [rbp+57h+arg_8], eax
0x140023576  test    cs:Microsoft_QuicEnableBits, 8
0x14002357d  jz      short loc_14002358F
0x14002357f  mov     r8d, [rbp+57h+arg_8]
0x140023583  lea     rdx, QuicApiExitStatus
0x14002358a  call    McTemplateU0q_EtwWriteTransfer
0x14002358f  mov     eax, [rbp+57h+arg_8]
0x140023592  jmp     short loc_140023599
0x140023594  mov     eax, 0C000000Dh
0x140023599  lea     r11, [rsp+0E0h+var_20]
0x1400235a1  mov     rbx, [r11+30h]
0x1400235a5  mov     rsi, [r11+40h]
0x1400235a9  mov     rsp, r11
0x1400235ac  pop     r15
0x1400235ae  pop     r14
0x1400235b0  pop     r12
0x1400235b2  pop     rdi
0x1400235b3  pop     rbp
0x1400235b4  retn
```
