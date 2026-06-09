# CscEaReadEaList

- ea: `0x14000cd00`
- end: `0x14000d2e8`
- name: `CscEaReadEaList`
- size: `1512`
- prototype: `__int64 __fastcall(unsigned __int64, __int64 **, __int64 *, _DWORD *)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x14000ccc0`
- `0x140054e88`
- `0x1400593dc`
- `0x14005b79c`
- `0x14005ecbc`
- `0x14006dd90`

## callees

- `0x14000c5f8`
- `0x14000cd00`
- `0x14000d744`
- `0x140018930`
- `0x14002f0f0`
- `0x14002f140`
- `0x14002f440`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000ce58`
- `ntoskrnl!ExAllocatePool2` at `0x14000cea8`
- `ntoskrnl!ExAllocatePool2` at `0x14000ce58`
- `ntoskrnl!ExAllocatePool2` at `0x14000cea8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cfe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cfe7`
- `ntoskrnl!KeInitializeEvent` at `0x14000d132`
- `ntoskrnl!KeInitializeEvent` at `0x14000d1cb`
- `ntoskrnl!KeInitializeEvent` at `0x14000d132`
- `ntoskrnl!KeInitializeEvent` at `0x14000d1cb`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000cd74`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000cf54`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000cd74`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000cf54`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d16c`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d194`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d205`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d22d`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d16c`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d194`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d205`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000d22d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000d03e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000d096`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000d03e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000d096`
- `ntoskrnl!IoGetStackLimits` at `0x14000cdbd`
- `ntoskrnl!IoGetStackLimits` at `0x14000cf94`
- `ntoskrnl!IoGetStackLimits` at `0x14000cdbd`
- `ntoskrnl!IoGetStackLimits` at `0x14000cf94`

## pseudocode

```c
__int64 __fastcall CscEaReadEaList(unsigned __int64 a1, __int64 **a2, __int64 *a3, _DWORD *a4)
{
  __int64 *v4; // r15
  _DWORD *v7; // r14
  int Blink; // edi
  unsigned int v9; // r8d
  __int64 **v10; // rcx
  int v11; // edx
  __int64 v12; // r13
  int v13; // r12d
  unsigned int v14; // edi
  __int64 **v15; // rcx
  int v16; // eax
  char *v17; // rax
  void *v18; // rsi
  __int64 **v19; // r15
  char *v20; // r14
  unsigned __int16 v21; // ax
  int v22; // ebx
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  bool v26; // zf
  __int64 v27; // rax
  BOOLEAN v28; // si
  __int64 v29; // rcx
  BOOLEAN v30; // di
  __int64 v31; // rcx
  struct _KEVENT Parameter; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+4Ch] [rbp-B4h] BYREF
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 LowLimit; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 HighLimit; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  void *v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 Pool2; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v41[18]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v42; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v43; // [rsp+160h] [rbp+60h]
  _DWORD *v44; // [rsp+168h] [rbp+68h]

  v44 = a4;
  v43 = a3;
  v42 = a1;
  v4 = a3;
  *a3 = 0;
  v33 = 0;
  v34 = 0;
  *a4 = 0;
  v7 = a4;
  memset(v41, 0, sizeof(v41));
  v41[5] = a1;
  v41[6] = &v34;
  v41[8] = &v33;
  v41[7] = 0x700000004LL;
  if ( KeAreAllApcsDisabled() )
  {
    memset(&Parameter, 0, sizeof(Parameter));
    KeInitializeEvent(&Parameter, NotificationEvent, 0);
    v41[0] = KeGetCurrentThread();
    v41[2] = CscStorepLowIoQueryInformationFilePostedRoutine;
    v41[4] = &Parameter;
    v41[1] = 0;
    LODWORD(v41[3]) = -1;
    v28 = KeSetKernelStackSwapEnable(0);
    Blink = CscStorepLowIoPostWorkItemAndWait(v29, v41, &Parameter);
    if ( v28 )
      KeSetKernelStackSwapEnable(v28);
    if ( Blink < 0 )
      return (unsigned int)Blink;
    Blink = v41[3];
  }
  else
  {
    Parameter.Header.WaitListHead.Blink = 0;
    Parameter.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v41;
    HighLimit = 0;
    *(_QWORD *)&Parameter.Header.Lock = CscStorepLowIoQueryInformationFilePostedRoutine;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&HighLimit - LowLimit >= (unsigned int)dword_14003BD20 )
    {
LABEL_3:
      Blink = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter.Header.Lock)(Parameter.Header.WaitListHead.Flink);
      goto LABEL_4;
    }
    v24 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &Parameter, 0x6000u, 0, 0);
    if ( v24 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
          (unsigned int)v24);
      }
      goto LABEL_3;
    }
    Blink = (int)Parameter.Header.WaitListHead.Blink;
  }
LABEL_4:
  if ( Blink < 0 )
    return (unsigned int)Blink;
  if ( v33 != 4 )
    return 3221226528LL;
  if ( v34 )
  {
    v9 = 0;
    if ( a2 )
    {
      v10 = a2;
      while ( 1 )
      {
        v11 = *((unsigned __int16 *)v10 + 8);
        v10 = (__int64 **)*v10;
        v9 += v11 + 9;
        if ( v10 == a2 )
          break;
        v9 = (v9 + 3) & 0xFFFFFFFC;
      }
    }
    LODWORD(LowLimit) = v9 + v34;
    Pool2 = ExAllocatePool2(258, v9 + v34, 624980803);
    v12 = Pool2;
    if ( Pool2 )
    {
      v35 = 0;
      v13 = 0;
      v14 = 0;
      if ( a2 )
      {
        v15 = a2;
        while ( 1 )
        {
          v16 = *((unsigned __int16 *)v15 + 8);
          v15 = (__int64 **)*v15;
          v14 += v16 + 6;
          if ( v15 == a2 )
            break;
          v14 = (v14 + 3) & 0xFFFFFFFC;
        }
      }
      v17 = (char *)ExAllocatePool2(258, v14, 624980803);
      v39 = v17;
      v18 = v17;
      if ( v17 )
      {
        v19 = a2;
        v20 = v17;
        while ( 1 )
        {
          *(_DWORD *)v20 = 0;
          v21 = *((_WORD *)v19 + 8);
          if ( v21 >= 0xFFu )
            break;
          v20[4] = v21;
          memmove(v20 + 5, v19[3], *((unsigned __int16 *)v19 + 8));
          v20[(unsigned __int8)v20[4] + 5] = 0;
          v19 = (__int64 **)*v19;
          if ( v19 == a2 )
          {
            memset(v41, 0, sizeof(v41));
            v41[5] = v42;
            LODWORD(v41[7]) = LowLimit;
            v41[12] = &v35;
            v41[6] = v12;
            BYTE4(v41[7]) = 0;
            v41[8] = v18;
            LODWORD(v41[9]) = v14;
            v41[10] = 0;
            LOBYTE(v41[11]) = 1;
            if ( KeAreAllApcsDisabled() )
            {
              memset(&Parameter, 0, sizeof(Parameter));
              KeInitializeEvent(&Parameter, NotificationEvent, 0);
              v41[0] = KeGetCurrentThread();
              v41[2] = CscStorepLowIoQueryEaFilePostedRoutine;
              v41[4] = &Parameter;
              v41[1] = 0;
              LODWORD(v41[3]) = -1;
              v30 = KeSetKernelStackSwapEnable(0);
              v22 = CscStorepLowIoPostWorkItemAndWait(v31, v41, &Parameter);
              if ( v30 )
                KeSetKernelStackSwapEnable(v30);
              if ( v22 >= 0 )
              {
                v22 = v41[3];
                goto LABEL_21;
              }
            }
            else
            {
              Parameter.Header.WaitListHead.Blink = 0;
              Parameter.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v41;
              v38 = 0;
              *(_QWORD *)&Parameter.Header.Lock = CscStorepLowIoQueryEaFilePostedRoutine;
              v42 = 0;
              IoGetStackLimits(&v42, &v38);
              if ( (unsigned __int64)&v38 - v42 >= (unsigned int)dword_14003BD20 )
                goto LABEL_20;
              v25 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &Parameter, 0x6000u, 0, 0);
              if ( v25 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    11,
                    WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
                    (unsigned int)v25);
                }
LABEL_20:
                v22 = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&Parameter.Header.Lock)(Parameter.Header.WaitListHead.Flink);
              }
              else
              {
                v22 = (int)Parameter.Header.WaitListHead.Blink;
              }
LABEL_21:
              if ( v22 >= 0 )
                v13 = v35;
            }
            v7 = v44;
            v4 = v43;
            goto LABEL_24;
          }
          v26 = (((unsigned __int8)v20[4] + 9) & 0xFFFFFFFC) == 0;
          v27 = ((unsigned __int8)v20[4] + 9) & 0xFFFFFFFC;
          *(_DWORD *)v20 = v27;
          if ( v26 )
            v20 = 0;
          else
            v20 += v27;
        }
        v7 = v44;
        v22 = -1073741811;
        v4 = v43;
      }
      else
      {
        v22 = -1073741670;
      }
      CscEaFreeFullEaBuffer(&v39);
      v18 = v39;
LABEL_24:
      if ( v18 )
        ExFreePoolWithTag(v18, 0x25407343u);
      if ( v22 >= 0 )
      {
        *v4 = v12;
        *v7 = v13;
        return (unsigned int)v22;
      }
    }
    else
    {
      v22 = -1073741670;
    }
    if ( v12 )
      CscEaFreeFullEaBuffer((void **)&Pool2);
    return (unsigned int)v22;
  }
  return 3221225554LL;
}

```

## disassembly

```asm
0x14000cd00  mov     [rsp-8+arg_18], r9
0x14000cd05  mov     [rsp-8+arg_10], r8
0x14000cd0a  mov     [rsp-8+arg_0], rcx
0x14000cd0f  push    rbp
0x14000cd10  push    rbx
0x14000cd11  push    rsi
0x14000cd12  push    rdi
0x14000cd13  push    r14
0x14000cd15  push    r15
0x14000cd17  lea     rbp, [rsp-18h]
0x14000cd1c  sub     rsp, 118h
0x14000cd23  xor     esi, esi
0x14000cd25  mov     r15, r8
0x14000cd28  mov     [r8], rsi
0x14000cd2b  mov     rbx, rdx
0x14000cd2e  mov     rdi, rcx
0x14000cd31  mov     [rsp+140h+var_F8], esi
0x14000cd35  mov     r8d, 90h; Size
0x14000cd3b  mov     [rsp+140h+var_F4], esi
0x14000cd3f  xor     edx, edx; Val
0x14000cd41  mov     [r9], esi
0x14000cd44  lea     rcx, [rbp+40h+var_C0]; void *
0x14000cd48  mov     r14, r9
0x14000cd4b  call    memset
0x14000cd50  lea     rax, [rsp+140h+var_F4]
0x14000cd55  mov     [rbp+40h+var_98], rdi
0x14000cd59  mov     [rbp+40h+var_90], rax
0x14000cd5d  lea     rax, [rsp+140h+var_F8]
0x14000cd62  mov     [rbp+40h+var_80], rax
0x14000cd66  mov     [rbp+40h+var_88], 4
0x14000cd6d  mov     [rbp+40h+var_84], 7
0x14000cd74  call    cs:__imp_KeAreAllApcsDisabled
0x14000cd7b  nop     dword ptr [rax+rax+00h]
0x14000cd80  lea     rdi, WPP_GLOBAL_Control
0x14000cd87  test    al, al
0x14000cd89  jnz     loc_14000D119
0x14000cd8f  lea     rax, [rbp+40h+var_C0]
0x14000cd93  mov     [rsp+140h+var_100], rsi
0x14000cd98  mov     qword ptr [rsp+140h+Parameter+8], rax
0x14000cd9d  lea     rdx, [rsp+140h+HighLimit]; HighLimit
0x14000cda2  lea     rax, CscStorepLowIoQueryInformationFilePostedRoutine
0x14000cda9  mov     [rsp+140h+HighLimit], rsi
0x14000cdae  lea     rcx, [rsp+140h+LowLimit]; LowLimit
0x14000cdb3  mov     qword ptr [rsp+140h+Parameter], rax
0x14000cdb8  mov     [rsp+140h+LowLimit], rsi
0x14000cdbd  call    cs:__imp_IoGetStackLimits
0x14000cdc4  nop     dword ptr [rax+rax+00h]
0x14000cdc9  mov     eax, cs:dword_14003BD20
0x14000cdcf  lea     rcx, [rsp+140h+HighLimit]
0x14000cdd4  sub     rcx, [rsp+140h+LowLimit]
0x14000cdd9  cmp     rcx, rax
0x14000cddc  jb      loc_14000D024
0x14000cde2  mov     rcx, qword ptr [rsp+140h+Parameter+8]
0x14000cde7  mov     rax, qword ptr [rsp+140h+Parameter]
0x14000cdec  call    _guard_dispatch_icall
0x14000cdf1  mov     edi, eax
0x14000cdf3  test    edi, edi
0x14000cdf5  js      loc_14000D112
0x14000cdfb  cmp     [rsp+140h+var_F8], 4
0x14000ce00  jnz     loc_14000D05B
0x14000ce06  mov     eax, [rsp+140h+var_F4]
0x14000ce0a  test    eax, eax
0x14000ce0c  jz      loc_14000D28B
0x14000ce12  mov     [rsp+140h+var_30], r13
0x14000ce1a  mov     r8d, esi
0x14000ce1d  test    rbx, rbx
0x14000ce20  jz      short loc_14000CE3C
0x14000ce22  mov     rcx, rbx
0x14000ce25  movzx   edx, word ptr [rcx+10h]
0x14000ce29  add     r8d, 9
0x14000ce2d  mov     rcx, [rcx]
0x14000ce30  add     r8d, edx
0x14000ce33  cmp     rcx, rbx
0x14000ce36  jnz     loc_14000D0CF
0x14000ce3c  add     eax, r8d
0x14000ce3f  mov     [rsp+140h+arg_8], r12
0x14000ce47  mov     edx, eax
0x14000ce49  mov     ecx, 102h
0x14000ce4e  mov     r8d, 25407343h
0x14000ce54  mov     dword ptr [rsp+140h+LowLimit], eax
0x14000ce58  call    cs:__imp_ExAllocatePool2
0x14000ce5f  nop     dword ptr [rax+rax+00h]
0x14000ce64  mov     [rsp+140h+var_C8], rax
0x14000ce69  mov     r13, rax
0x14000ce6c  test    rax, rax
0x14000ce6f  jz      loc_14000D0DC
0x14000ce75  mov     [rsp+140h+var_F0], esi
0x14000ce79  mov     r12d, esi
0x14000ce7c  mov     edi, esi
0x14000ce7e  test    rbx, rbx
0x14000ce81  jz      short loc_14000CE9B
0x14000ce83  mov     rcx, rbx
0x14000ce86  movzx   eax, word ptr [rcx+10h]
0x14000ce8a  add     edi, 6
0x14000ce8d  mov     rcx, [rcx]
0x14000ce90  add     edi, eax
0x14000ce92  cmp     rcx, rbx
0x14000ce95  jnz     loc_14000D071
0x14000ce9b  mov     edx, edi
0x14000ce9d  mov     ecx, 102h
0x14000cea2  mov     r8d, 25407343h
0x14000cea8  call    cs:__imp_ExAllocatePool2
0x14000ceaf  nop     dword ptr [rax+rax+00h]
0x14000ceb4  mov     [rsp+140h+var_D0], rax
0x14000ceb9  mov     rsi, rax
0x14000cebc  test    rax, rax
0x14000cebf  jz      loc_14000D0F9
0x14000cec5  mov     r15, rbx
0x14000cec8  mov     r14, rax
0x14000cecb  mov     dword ptr [r14], 0
0x14000ced2  mov     ecx, 0FFh
0x14000ced7  movzx   eax, word ptr [r15+10h]
0x14000cedc  cmp     ax, cx
0x14000cedf  jnb     loc_14000D2D6
0x14000cee5  mov     [r14+4], al
0x14000cee9  lea     rcx, [r14+5]; void *
0x14000ceed  movzx   r8d, word ptr [r15+10h]; Size
0x14000cef2  mov     rdx, [r15+18h]; Src
0x14000cef6  call    memmove
0x14000cefb  movzx   eax, byte ptr [r14+4]
0x14000cf00  mov     byte ptr [rax+r14+5], 0
0x14000cf06  mov     r15, [r15]
0x14000cf09  cmp     r15, rbx
0x14000cf0c  jnz     loc_14000D0B3
0x14000cf12  xor     edx, edx; Val
0x14000cf14  lea     rcx, [rbp+40h+var_C0]; void *
0x14000cf18  mov     r8d, 90h; Size
0x14000cf1e  call    memset
0x14000cf23  mov     rax, [rbp+40h+arg_0]
0x14000cf27  xor     ebx, ebx
0x14000cf29  mov     [rbp+40h+var_98], rax
0x14000cf2d  mov     eax, dword ptr [rsp+140h+LowLimit]
0x14000cf31  mov     [rbp+40h+var_88], eax
0x14000cf34  lea     rax, [rsp+140h+var_F0]
0x14000cf39  mov     [rbp+40h+var_60], rax
0x14000cf3d  mov     [rbp+40h+var_90], r13
0x14000cf41  mov     byte ptr [rbp+40h+var_84], 0
0x14000cf45  mov     [rbp+40h+var_80], rsi
0x14000cf49  mov     [rbp+40h+var_78], edi
0x14000cf4c  mov     [rbp+40h+var_70], rbx
0x14000cf50  mov     [rbp+40h+var_68], 1
0x14000cf54  call    cs:__imp_KeAreAllApcsDisabled
0x14000cf5b  nop     dword ptr [rax+rax+00h]
0x14000cf60  test    al, al
0x14000cf62  jnz     loc_14000D1B2
0x14000cf68  lea     rax, [rbp+40h+var_C0]
0x14000cf6c  mov     [rsp+140h+var_100], rbx
0x14000cf71  mov     qword ptr [rsp+140h+Parameter+8], rax
0x14000cf76  lea     rdx, [rsp+140h+var_D8]; HighLimit
0x14000cf7b  lea     rax, CscStorepLowIoQueryEaFilePostedRoutine
0x14000cf82  mov     [rsp+140h+var_D8], rbx
0x14000cf87  lea     rcx, [rbp+40h+arg_0]; LowLimit
0x14000cf8b  mov     qword ptr [rsp+140h+Parameter], rax
0x14000cf90  mov     [rbp+40h+arg_0], rbx
0x14000cf94  call    cs:__imp_IoGetStackLimits
0x14000cf9b  nop     dword ptr [rax+rax+00h]
0x14000cfa0  mov     eax, cs:dword_14003BD20
0x14000cfa6  lea     rcx, [rsp+140h+var_D8]
0x14000cfab  sub     rcx, [rbp+40h+arg_0]
0x14000cfaf  cmp     rcx, rax
0x14000cfb2  jb      loc_14000D07C
0x14000cfb8  mov     rcx, qword ptr [rsp+140h+Parameter+8]
0x14000cfbd  mov     rax, qword ptr [rsp+140h+Parameter]
0x14000cfc2  call    _guard_dispatch_icall
0x14000cfc7  mov     ebx, eax
0x14000cfc9  test    ebx, ebx
0x14000cfcb  js      short loc_14000CFD2
0x14000cfcd  mov     r12d, [rsp+140h+var_F0]
0x14000cfd2  mov     r14, [rbp+40h+arg_18]
0x14000cfd6  mov     r15, [rbp+40h+arg_10]
0x14000cfda  test    rsi, rsi
0x14000cfdd  jz      short loc_14000CFF3
0x14000cfdf  mov     edx, 25407343h; Tag
0x14000cfe4  mov     rcx, rsi; P
0x14000cfe7  call    cs:__imp_ExFreePoolWithTag
0x14000cfee  nop     dword ptr [rax+rax+00h]
0x14000cff3  test    ebx, ebx
0x14000cff5  js      loc_14000D0E1
0x14000cffb  mov     [r15], r13
0x14000cffe  mov     [r14], r12d
0x14000d001  mov     r13, [rsp+140h+var_30]
0x14000d009  mov     eax, ebx
0x14000d00b  mov     r12, [rsp+140h+arg_8]
0x14000d013  add     rsp, 118h
0x14000d01a  pop     r15
0x14000d01c  pop     r14
0x14000d01e  pop     rdi
0x14000d01f  pop     rsi
0x14000d020  pop     rbx
0x14000d021  pop     rbp
0x14000d022  retn
0x14000d024  xor     r9d, r9d; Wait
0x14000d027  mov     [rsp+140h+Context], rsi; Context
0x14000d02c  mov     r8d, 6000h; Size
0x14000d032  lea     rdx, [rsp+140h+Parameter]; Parameter
0x14000d037  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x14000d03e  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000d045  nop     dword ptr [rax+rax+00h]
0x14000d04a  test    eax, eax
0x14000d04c  js      loc_14000D251
0x14000d052  mov     edi, dword ptr [rsp+140h+var_100]
0x14000d056  jmp     loc_14000CDF3
0x14000d05b  mov     eax, 0C0000420h
0x14000d060  add     rsp, 118h
0x14000d067  pop     r15
0x14000d069  pop     r14
0x14000d06b  pop     rdi
0x14000d06c  pop     rsi
0x14000d06d  pop     rbx
0x14000d06e  pop     rbp
0x14000d06f  retn
0x14000d071  add     edi, 3
0x14000d074  and     edi, 0FFFFFFFCh
0x14000d077  jmp     loc_14000CE86
0x14000d07c  xor     r9d, r9d; Wait
0x14000d07f  mov     [rsp+140h+Context], rbx; Context
0x14000d084  mov     r8d, 6000h; Size
0x14000d08a  lea     rdx, [rsp+140h+Parameter]; Parameter
0x14000d08f  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x14000d096  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000d09d  nop     dword ptr [rax+rax+00h]
0x14000d0a2  test    eax, eax
0x14000d0a4  js      loc_14000D295
0x14000d0aa  mov     ebx, dword ptr [rsp+140h+var_100]
0x14000d0ae  jmp     loc_14000CFC9
0x14000d0b3  movzx   eax, byte ptr [r14+4]
0x14000d0b8  add     eax, 9
0x14000d0bb  and     eax, 0FFFFFFFCh
0x14000d0be  mov     [r14], eax
0x14000d0c1  jz      loc_14000D249
0x14000d0c7  add     r14, rax
0x14000d0ca  jmp     loc_14000CECB
0x14000d0cf  add     r8d, 3
0x14000d0d3  and     r8d, 0FFFFFFFCh
0x14000d0d7  jmp     loc_14000CE25
0x14000d0dc  mov     ebx, 0C000009Ah
0x14000d0e1  test    r13, r13
0x14000d0e4  jz      loc_14000D001
0x14000d0ea  lea     rcx, [rsp+140h+var_C8]
0x14000d0ef  call    CscEaFreeFullEaBuffer
0x14000d0f4  jmp     loc_14000D001
0x14000d0f9  mov     ebx, 0C000009Ah
0x14000d0fe  lea     rcx, [rsp+140h+var_D0]
0x14000d103  call    CscEaFreeFullEaBuffer
0x14000d108  mov     rsi, [rsp+140h+var_D0]
0x14000d10d  jmp     loc_14000CFDA
0x14000d112  mov     eax, edi
0x14000d114  jmp     loc_14000D013
0x14000d119  xorps   xmm0, xmm0
0x14000d11c  lea     rcx, [rsp+140h+Parameter]; Event
0x14000d121  xor     eax, eax
0x14000d123  xor     r8d, r8d; State
0x14000d126  xor     edx, edx; Type
0x14000d128  mov     [rsp+140h+var_100], rax
0x14000d12d  movups  [rsp+140h+Parameter], xmm0
0x14000d132  call    cs:__imp_KeInitializeEvent
0x14000d139  nop     dword ptr [rax+rax+00h]
0x14000d13e  mov     rax, gs:188h
0x14000d147  xor     ecx, ecx; Enable
0x14000d149  mov     [rbp+40h+var_C0], rax
0x14000d14d  lea     rax, CscStorepLowIoQueryInformationFilePostedRoutine
0x14000d154  mov     [rbp+40h+var_B0], rax
0x14000d158  lea     rax, [rsp+140h+Parameter]
0x14000d15d  mov     [rbp+40h+var_A0], rax
0x14000d161  mov     [rbp+40h+var_B8], rsi
0x14000d165  mov     [rbp+40h+var_A8], 0FFFFFFFFh
0x14000d16c  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000d173  nop     dword ptr [rax+rax+00h]
0x14000d178  lea     r8, [rsp+140h+Parameter]
0x14000d17d  movzx   esi, al
0x14000d180  lea     rdx, [rbp+40h+var_C0]
0x14000d184  call    CscStorepLowIoPostWorkItemAndWait
0x14000d189  mov     edi, eax
0x14000d18b  test    sil, sil
0x14000d18e  jz      short loc_14000D1A0
0x14000d190  movzx   ecx, sil; Enable
0x14000d194  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000d19b  nop     dword ptr [rax+rax+00h]
0x14000d1a0  test    edi, edi
0x14000d1a2  js      loc_14000D112
0x14000d1a8  mov     edi, [rbp+40h+var_A8]
0x14000d1ab  xor     esi, esi
0x14000d1ad  jmp     loc_14000CDF3
0x14000d1b2  xorps   xmm0, xmm0
0x14000d1b5  lea     rcx, [rsp+140h+Parameter]; Event
0x14000d1ba  xor     eax, eax
0x14000d1bc  xor     r8d, r8d; State
0x14000d1bf  xor     edx, edx; Type
0x14000d1c1  mov     [rsp+140h+var_100], rax
0x14000d1c6  movups  [rsp+140h+Parameter], xmm0
0x14000d1cb  call    cs:__imp_KeInitializeEvent
0x14000d1d2  nop     dword ptr [rax+rax+00h]
0x14000d1d7  mov     rax, gs:188h
0x14000d1e0  xor     ecx, ecx; Enable
0x14000d1e2  mov     [rbp+40h+var_C0], rax
0x14000d1e6  lea     rax, CscStorepLowIoQueryEaFilePostedRoutine
0x14000d1ed  mov     [rbp+40h+var_B0], rax
0x14000d1f1  lea     rax, [rsp+140h+Parameter]
0x14000d1f6  mov     [rbp+40h+var_A0], rax
0x14000d1fa  mov     [rbp+40h+var_B8], rbx
  ... truncated ...
```
