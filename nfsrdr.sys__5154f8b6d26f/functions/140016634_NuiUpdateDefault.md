# NuiUpdateDefault

- ea: `0x140016634`
- end: `0x140016a9f`
- name: `NuiUpdateDefault`
- size: `1131`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140016b14`
- `0x140016cb8`

## callees

- `0x1400159cc`
- `0x140016634`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140016671`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016671`
- `ntoskrnl!KeReleaseMutex` at `0x140016a1b`
- `ntoskrnl!KeReleaseMutex` at `0x140016a67`
- `ntoskrnl!KeReleaseMutex` at `0x140016a80`
- `ntoskrnl!KeReleaseMutex` at `0x140016a1b`
- `ntoskrnl!KeReleaseMutex` at `0x140016a67`
- `ntoskrnl!KeReleaseMutex` at `0x140016a80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016703`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400167b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016861`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016703`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400167b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016861`
- `ntoskrnl!ExAllocatePool2` at `0x140016726`
- `ntoskrnl!ExAllocatePool2` at `0x1400167cd`
- `ntoskrnl!ExAllocatePool2` at `0x14001687e`
- `ntoskrnl!ExAllocatePool2` at `0x140016918`
- `ntoskrnl!ExAllocatePool2` at `0x1400169c5`
- `ntoskrnl!ExAllocatePool2` at `0x140016726`
- `ntoskrnl!ExAllocatePool2` at `0x1400167cd`
- `ntoskrnl!ExAllocatePool2` at `0x14001687e`
- `ntoskrnl!ExAllocatePool2` at `0x140016918`
- `ntoskrnl!ExAllocatePool2` at `0x1400169c5`

## pseudocode

```c
__int64 __fastcall NuiUpdateDefault(
        _DWORD *a1,
        const void **a2,
        const void **a3,
        const void **a4,
        int a5,
        char a6,
        _OWORD *a7,
        _OWORD *a8)
{
  char *v13; // rdi
  unsigned int v14; // ebx
  unsigned int i; // edx
  __int64 v16; // rcx
  void *v17; // rcx
  _QWORD *v18; // rbx
  void *v19; // rcx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rbx
  _OWORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rbx
  _OWORD *v31; // rcx

  if ( !a1 )
    return 0;
  KeWaitForSingleObject(Mutex, Executive, 0, 0, 0);
  v13 = (char *)P;
  if ( P )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= dword_140041360 || (v16 = *(_QWORD *)v13) == 0 )
      {
        KeReleaseMutex((PRKMUTEX)Mutex, 0);
        return 3221225473LL;
      }
      if ( *a1 == *(_DWORD *)v16 && a1[1] == *(_DWORD *)(v16 + 4) )
        break;
      v13 += 8;
    }
    if ( (a6 & 0x10) != 0 )
    {
      if ( a5 )
        *(_DWORD *)(*(_QWORD *)(v16 + 8) + 24LL) = a5;
      if ( a2 )
      {
        v17 = **(void ***)(*(_QWORD *)v13 + 8LL);
        if ( v17 )
          ExFreePoolWithTag(v17, 0);
        v18 = *(_QWORD **)(*(_QWORD *)v13 + 8LL);
        *v18 = ExAllocatePool2(258, *(unsigned __int16 *)a2 + 2LL, 1716676174);
        v19 = **(void ***)(*(_QWORD *)v13 + 8LL);
        if ( !v19 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v21 = 21;
            goto LABEL_50;
          }
LABEL_51:
          KeReleaseMutex((PRKMUTEX)Mutex, 0);
          return 3221225626LL;
        }
        memmove(v19, a2[1], *(unsigned __int16 *)a2);
        *(_WORD *)(**(_QWORD **)(*(_QWORD *)v13 + 8LL) + 2 * ((unsigned __int64)*(unsigned __int16 *)a2 >> 1)) = 0;
      }
      if ( a3 )
      {
        v22 = *(void **)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 8LL);
        if ( v22 )
          ExFreePoolWithTag(v22, 0);
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 8LL) = ExAllocatePool2(
                                                                 258,
                                                                 *(unsigned __int16 *)a3 + 2LL,
                                                                 1632790094);
        v23 = *(void **)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 8LL);
        if ( !v23 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_51;
          }
          v21 = 22;
          goto LABEL_50;
        }
        memmove(v23, a3[1], *(unsigned __int16 *)a3);
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 8LL)
                 + 2 * ((unsigned __int64)*(unsigned __int16 *)a3 >> 1)) = 0;
      }
      if ( a4 )
      {
        v24 = *(void **)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 16LL);
        if ( v24 )
          ExFreePoolWithTag(v24, 0);
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 16LL) = ExAllocatePool2(
                                                                  258,
                                                                  *(unsigned __int16 *)a4 + 2LL,
                                                                  1649567310);
        v25 = *(void **)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 16LL);
        if ( !v25 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_51;
          }
          v21 = 23;
          goto LABEL_50;
        }
        memmove(v25, a4[1], *(unsigned __int16 *)a4);
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 16LL)
                 + 2 * ((unsigned __int64)*(unsigned __int16 *)a4 >> 1)) = 0;
      }
      v26 = *(_QWORD *)v13;
      if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 32LL) )
      {
        v27 = *(_QWORD *)(*(_QWORD *)v13 + 8LL);
        *(_QWORD *)(v27 + 32) = ExAllocatePool2(258, 76, 1431463502);
        v26 = *(_QWORD *)v13;
        if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 32LL) )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_51;
          }
          v21 = 24;
          goto LABEL_50;
        }
      }
      v28 = *(_OWORD **)(*(_QWORD *)(v26 + 8) + 32LL);
      *v28 = *a7;
      v28[1] = a7[1];
      v28[2] = a7[2];
      v28[3] = a7[3];
      *(_OWORD *)((char *)v28 + 60) = *(_OWORD *)((char *)a7 + 60);
    }
    if ( (a6 & 0x20) != 0 )
    {
      v29 = *(_QWORD *)v13;
      if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 40LL) )
      {
        v30 = *(_QWORD *)(*(_QWORD *)v13 + 8LL);
        *(_QWORD *)(v30 + 40) = ExAllocatePool2(258, 64, 1330800206);
        v29 = *(_QWORD *)v13;
        if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 40LL) )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_51;
          }
          v21 = 25;
LABEL_50:
          WPP_SF_(v20->AttachedDevice, v21, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids);
          goto LABEL_51;
        }
      }
      v31 = *(_OWORD **)(*(_QWORD *)(v29 + 8) + 40LL);
      *v31 = *a8;
      v31[1] = a8[1];
      v31[2] = a8[2];
      v31[3] = a8[3];
    }
    v14 = 0;
  }
  else
  {
    v14 = -1073741823;
  }
  KeReleaseMutex((PRKMUTEX)Mutex, 0);
  return v14;
}

```

## disassembly

```asm
0x140016634  push    rbx
0x140016636  push    rbp
0x140016637  push    rsi
0x140016638  push    rdi
0x140016639  push    r13
0x14001663b  push    r14
0x14001663d  sub     rsp, 38h
0x140016641  mov     rbp, r9
0x140016644  mov     r14, r8
0x140016647  mov     rsi, rdx
0x14001664a  mov     rbx, rcx
0x14001664d  test    rcx, rcx
0x140016650  jnz     short loc_140016659
0x140016652  xor     eax, eax
0x140016654  jmp     loc_140016A91
0x140016659  mov     rcx, cs:Mutex; Object
0x140016660  xor     r9d, r9d; Alertable
0x140016663  xor     r8d, r8d; WaitMode
0x140016666  mov     [rsp+68h+Timeout], 0; Timeout
0x14001666f  xor     edx, edx; WaitReason
0x140016671  call    cs:__imp_KeWaitForSingleObject
0x140016678  nop     dword ptr [rax+rax+00h]
0x14001667d  mov     rdi, cs:P
0x140016684  test    rdi, rdi
0x140016687  jnz     short loc_140016693
0x140016689  mov     ebx, 0C0000001h
0x14001668e  jmp     loc_140016A5E
0x140016693  xor     edx, edx
0x140016695  cmp     edx, cs:dword_140041360
0x14001669b  jnb     loc_140016A77
0x1400166a1  mov     rcx, [rdi]
0x1400166a4  test    rcx, rcx
0x1400166a7  jz      loc_140016A77
0x1400166ad  mov     eax, [rcx]
0x1400166af  cmp     [rbx], eax
0x1400166b1  jnz     short loc_1400166BB
0x1400166b3  mov     eax, [rcx+4]
0x1400166b6  cmp     [rbx+4], eax
0x1400166b9  jz      short loc_1400166C3
0x1400166bb  inc     edx
0x1400166bd  add     rdi, 8
0x1400166c1  jmp     short loc_140016695
0x1400166c3  test    [rsp+68h+arg_28], 10h
0x1400166cb  mov     r13d, 102h
0x1400166d1  jz      loc_140016998
0x1400166d7  mov     edx, [rsp+68h+arg_20]
0x1400166de  test    edx, edx
0x1400166e0  jz      short loc_1400166E9
0x1400166e2  mov     rax, [rcx+8]
0x1400166e6  mov     [rax+18h], edx
0x1400166e9  test    rsi, rsi
0x1400166ec  jz      loc_140016795
0x1400166f2  mov     rax, [rdi]
0x1400166f5  mov     rcx, [rax+8]
0x1400166f9  mov     rcx, [rcx]; P
0x1400166fc  test    rcx, rcx
0x1400166ff  jz      short loc_14001670F
0x140016701  xor     edx, edx; Tag
0x140016703  call    cs:__imp_ExFreePoolWithTag
0x14001670a  nop     dword ptr [rax+rax+00h]
0x14001670f  mov     rax, [rdi]
0x140016712  mov     r8d, 6652664Eh
0x140016718  movzx   edx, word ptr [rsi]
0x14001671b  mov     rcx, r13
0x14001671e  add     rdx, 2
0x140016722  mov     rbx, [rax+8]
0x140016726  call    cs:__imp_ExAllocatePool2
0x14001672d  nop     dword ptr [rax+rax+00h]
0x140016732  mov     [rbx], rax
0x140016735  mov     rax, [rdi]
0x140016738  mov     rcx, [rax+8]
0x14001673c  mov     rcx, [rcx]; void *
0x14001673f  test    rcx, rcx
0x140016742  jnz     short loc_140016770
0x140016744  mov     rcx, cs:WPP_GLOBAL_Control
0x14001674b  lea     rax, WPP_GLOBAL_Control
0x140016752  cmp     rcx, rax
0x140016755  jz      loc_140016A12
0x14001675b  mov     eax, [rcx+2Ch]
0x14001675e  test    al, 1
0x140016760  jz      loc_140016A12
0x140016766  mov     edx, 15h
0x14001676b  jmp     loc_140016A02
0x140016770  movzx   r8d, word ptr [rsi]; Size
0x140016774  mov     rdx, [rsi+8]; Src
0x140016778  call    memmove
0x14001677d  mov     rax, [rdi]
0x140016780  movzx   r8d, word ptr [rsi]
0x140016784  shr     r8, 1
0x140016787  mov     rcx, [rax+8]
0x14001678b  xor     eax, eax
0x14001678d  mov     rdx, [rcx]
0x140016790  mov     [rdx+r8*2], ax
0x140016795  test    r14, r14
0x140016798  jz      loc_140016846
0x14001679e  mov     rax, [rdi]
0x1400167a1  mov     rcx, [rax+8]
0x1400167a5  mov     rcx, [rcx+8]; P
0x1400167a9  test    rcx, rcx
0x1400167ac  jz      short loc_1400167BC
0x1400167ae  xor     edx, edx; Tag
0x1400167b0  call    cs:__imp_ExFreePoolWithTag
0x1400167b7  nop     dword ptr [rax+rax+00h]
0x1400167bc  movzx   edx, word ptr [r14]
0x1400167c0  mov     r8d, 6152664Eh
0x1400167c6  add     rdx, 2
0x1400167ca  mov     rcx, r13
0x1400167cd  call    cs:__imp_ExAllocatePool2
0x1400167d4  nop     dword ptr [rax+rax+00h]
0x1400167d9  mov     rcx, [rdi]
0x1400167dc  mov     rdx, [rcx+8]
0x1400167e0  mov     [rdx+8], rax
0x1400167e4  mov     rax, [rdi]
0x1400167e7  mov     rcx, [rax+8]
0x1400167eb  mov     rcx, [rcx+8]; void *
0x1400167ef  test    rcx, rcx
0x1400167f2  jnz     short loc_140016820
0x1400167f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167fb  lea     rax, WPP_GLOBAL_Control
0x140016802  cmp     rcx, rax
0x140016805  jz      loc_140016A12
0x14001680b  mov     eax, [rcx+2Ch]
0x14001680e  test    al, 1
0x140016810  jz      loc_140016A12
0x140016816  mov     edx, 16h
0x14001681b  jmp     loc_140016A02
0x140016820  movzx   r8d, word ptr [r14]; Size
0x140016824  mov     rdx, [r14+8]; Src
0x140016828  call    memmove
0x14001682d  mov     rax, [rdi]
0x140016830  movzx   r8d, word ptr [r14]
0x140016834  shr     r8, 1
0x140016837  mov     rcx, [rax+8]
0x14001683b  xor     eax, eax
0x14001683d  mov     rdx, [rcx+8]
0x140016841  mov     [rdx+r8*2], ax
0x140016846  test    rbp, rbp
0x140016849  jz      loc_1400168F9
0x14001684f  mov     rax, [rdi]
0x140016852  mov     rcx, [rax+8]
0x140016856  mov     rcx, [rcx+10h]; P
0x14001685a  test    rcx, rcx
0x14001685d  jz      short loc_14001686D
0x14001685f  xor     edx, edx; Tag
0x140016861  call    cs:__imp_ExFreePoolWithTag
0x140016868  nop     dword ptr [rax+rax+00h]
0x14001686d  movzx   edx, word ptr [rbp+0]
0x140016871  mov     r8d, 6252664Eh
0x140016877  add     rdx, 2
0x14001687b  mov     rcx, r13
0x14001687e  call    cs:__imp_ExAllocatePool2
0x140016885  nop     dword ptr [rax+rax+00h]
0x14001688a  mov     rcx, [rdi]
0x14001688d  mov     rdx, [rcx+8]
0x140016891  mov     [rdx+10h], rax
0x140016895  mov     rax, [rdi]
0x140016898  mov     rcx, [rax+8]
0x14001689c  mov     rcx, [rcx+10h]; void *
0x1400168a0  test    rcx, rcx
0x1400168a3  jnz     short loc_1400168D1
0x1400168a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400168ac  lea     rax, WPP_GLOBAL_Control
0x1400168b3  cmp     rcx, rax
0x1400168b6  jz      loc_140016A12
0x1400168bc  mov     eax, [rcx+2Ch]
0x1400168bf  test    al, 1
0x1400168c1  jz      loc_140016A12
0x1400168c7  mov     edx, 17h
0x1400168cc  jmp     loc_140016A02
0x1400168d1  movzx   r8d, word ptr [rbp+0]; Size
0x1400168d6  mov     rdx, [rbp+8]; Src
0x1400168da  call    memmove
0x1400168df  mov     rax, [rdi]
0x1400168e2  movzx   r8d, word ptr [rbp+0]
0x1400168e7  shr     r8, 1
0x1400168ea  mov     rcx, [rax+8]
0x1400168ee  xor     eax, eax
0x1400168f0  mov     rdx, [rcx+10h]
0x1400168f4  mov     [rdx+r8*2], ax
0x1400168f9  mov     rcx, [rdi]
0x1400168fc  mov     rax, [rcx+8]
0x140016900  cmp     qword ptr [rax+20h], 0
0x140016905  jnz     short loc_140016962
0x140016907  mov     edx, 4Ch ; 'L'
0x14001690c  mov     r8d, 5552664Eh
0x140016912  mov     rcx, r13
0x140016915  mov     rbx, rax
0x140016918  call    cs:__imp_ExAllocatePool2
0x14001691f  nop     dword ptr [rax+rax+00h]
0x140016924  mov     [rbx+20h], rax
0x140016928  mov     rcx, [rdi]
0x14001692b  mov     rax, [rcx+8]
0x14001692f  cmp     qword ptr [rax+20h], 0
0x140016934  jnz     short loc_140016962
0x140016936  mov     rcx, cs:WPP_GLOBAL_Control
0x14001693d  lea     rax, WPP_GLOBAL_Control
0x140016944  cmp     rcx, rax
0x140016947  jz      loc_140016A12
0x14001694d  mov     eax, [rcx+2Ch]
0x140016950  test    al, 1
0x140016952  jz      loc_140016A12
0x140016958  mov     edx, 18h
0x14001695d  jmp     loc_140016A02
0x140016962  mov     rax, [rcx+8]
0x140016966  mov     rcx, [rax+20h]
0x14001696a  mov     rax, [rsp+68h+arg_30]
0x140016972  movaps  xmm0, xmmword ptr [rax]
0x140016975  movups  xmmword ptr [rcx], xmm0
0x140016978  movaps  xmm1, xmmword ptr [rax+10h]
0x14001697c  movups  xmmword ptr [rcx+10h], xmm1
0x140016980  movaps  xmm0, xmmword ptr [rax+20h]
0x140016984  movups  xmmword ptr [rcx+20h], xmm0
0x140016988  movaps  xmm1, xmmword ptr [rax+30h]
0x14001698c  movups  xmmword ptr [rcx+30h], xmm1
0x140016990  movups  xmm0, xmmword ptr [rax+3Ch]
0x140016994  movups  xmmword ptr [rcx+3Ch], xmm0
0x140016998  test    [rsp+68h+arg_28], 20h
0x1400169a0  jz      loc_140016A5C
0x1400169a6  mov     rdx, [rdi]
0x1400169a9  mov     rax, [rdx+8]
0x1400169ad  cmp     qword ptr [rax+28h], 0
0x1400169b2  jnz     short loc_140016A2E
0x1400169b4  mov     edx, 40h ; '@'
0x1400169b9  mov     r8d, 4F52664Eh
0x1400169bf  mov     rcx, r13
0x1400169c2  mov     rbx, rax
0x1400169c5  call    cs:__imp_ExAllocatePool2
0x1400169cc  nop     dword ptr [rax+rax+00h]
0x1400169d1  mov     [rbx+28h], rax
0x1400169d5  mov     rdx, [rdi]
0x1400169d8  mov     rax, [rdx+8]
0x1400169dc  cmp     qword ptr [rax+28h], 0
0x1400169e1  jnz     short loc_140016A2E
0x1400169e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400169ea  lea     rax, WPP_GLOBAL_Control
0x1400169f1  cmp     rcx, rax
0x1400169f4  jz      short loc_140016A12
0x1400169f6  mov     eax, [rcx+2Ch]
0x1400169f9  test    al, 1
0x1400169fb  jz      short loc_140016A12
0x1400169fd  mov     edx, 19h
0x140016a02  mov     rcx, [rcx+18h]
0x140016a06  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x140016a0d  call    WPP_SF_
0x140016a12  mov     rcx, cs:Mutex; Mutex
0x140016a19  xor     edx, edx; Wait
0x140016a1b  call    cs:__imp_KeReleaseMutex
0x140016a22  nop     dword ptr [rax+rax+00h]
0x140016a27  mov     eax, 0C000009Ah
0x140016a2c  jmp     short loc_140016A91
0x140016a2e  mov     rax, [rdx+8]
0x140016a32  mov     rcx, [rax+28h]
0x140016a36  mov     rax, [rsp+68h+arg_38]
0x140016a3e  movups  xmm0, xmmword ptr [rax]
0x140016a41  movups  xmmword ptr [rcx], xmm0
0x140016a44  movups  xmm1, xmmword ptr [rax+10h]
0x140016a48  movups  xmmword ptr [rcx+10h], xmm1
0x140016a4c  movups  xmm0, xmmword ptr [rax+20h]
0x140016a50  movups  xmmword ptr [rcx+20h], xmm0
0x140016a54  movups  xmm1, xmmword ptr [rax+30h]
0x140016a58  movups  xmmword ptr [rcx+30h], xmm1
0x140016a5c  xor     ebx, ebx
0x140016a5e  mov     rcx, cs:Mutex; Mutex
0x140016a65  xor     edx, edx; Wait
0x140016a67  call    cs:__imp_KeReleaseMutex
0x140016a6e  nop     dword ptr [rax+rax+00h]
0x140016a73  mov     eax, ebx
0x140016a75  jmp     short loc_140016A91
0x140016a77  mov     rcx, cs:Mutex; Mutex
0x140016a7e  xor     edx, edx; Wait
0x140016a80  call    cs:__imp_KeReleaseMutex
0x140016a87  nop     dword ptr [rax+rax+00h]
0x140016a8c  mov     eax, 0C0000001h
0x140016a91  add     rsp, 38h
0x140016a95  pop     r14
0x140016a97  pop     r13
0x140016a99  pop     rdi
0x140016a9a  pop     rsi
0x140016a9b  pop     rbp
0x140016a9c  pop     rbx
0x140016a9d  retn
```
