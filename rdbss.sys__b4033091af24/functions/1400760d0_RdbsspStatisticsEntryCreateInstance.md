# RdbsspStatisticsEntryCreateInstance

- ea: `0x1400760d0`
- end: `0x14007649d`
- name: `RdbsspStatisticsEntryCreateInstance`
- size: `973`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14005a030`

## callees

- `0x140016e20`
- `0x140016e70`
- `0x1400255e8`
- `0x140025740`
- `0x140025d00`
- `0x140025d80`
- `0x14005220c`
- `0x1400760d0`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400761f1`
- `ntoskrnl!RtlLengthSid` at `0x1400762d7`
- `ntoskrnl!RtlLengthSid` at `0x1400761f1`
- `ntoskrnl!RtlLengthSid` at `0x1400762d7`

## pseudocode

```c
__int64 __fastcall RdbsspStatisticsEntryCreateInstance(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        PSID Sid,
        const void **a6,
        const void **a7,
        __int64 *a8)
{
  char v8; // r10
  int v9; // r8d
  int v11; // r15d
  PSID v12; // r12
  const void **v13; // r14
  const void **v14; // r13
  ULONG v15; // edi
  __int64 v16; // rax
  __int64 v17; // rsi
  char *v18; // rbx
  ULONG v19; // eax
  __int64 v20; // rdi
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax

  v8 = a3;
  v9 = a2;
  v11 = 0;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v12 = Sid;
  }
  else
  {
    v12 = Sid;
    WPP_SF_qqDDq(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      (unsigned int)WPP_fa472c519fe6315f206bfef5f05c0219_Traceguids,
      a1,
      a2,
      v8,
      a4,
      (char)Sid);
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v13 = a7;
    v14 = a6;
  }
  else
  {
    v13 = a7;
    v14 = a6;
    WPP_SF_ZZq(WPP_GLOBAL_Control->AttachedDevice, a2, v9, (_DWORD)a6, (__int64)a7, (char)a8);
  }
  v15 = 340;
  if ( v12 )
    v15 = RtlLengthSid(v12) + 340;
  if ( v14 )
  {
    v22 = *(unsigned __int16 *)v14;
    if ( (_WORD)v22 )
      v15 += v22;
  }
  if ( v13 )
  {
    v23 = *(unsigned __int16 *)v13;
    if ( (_WORD)v23 )
      v15 += v23;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(a1 + 16))(a1, 64, v15, 1163093074);
  v17 = v16;
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64, __int64))(a1 + 72))(a1, v16 + 24);
    *(_QWORD *)v17 = a1;
    *(_QWORD *)(v17 + 16) = a2;
    *(_DWORD *)(v17 + 32) = 1;
    *(_DWORD *)(v17 + 308) = a3;
    *(_QWORD *)(v17 + 312) = a2;
    *(_DWORD *)(v17 + 324) = a4;
    v18 = (char *)(v17 + 340);
    if ( v12 )
    {
      v19 = RtlLengthSid(v12);
      *(_DWORD *)(v17 + 328) = v19;
      v20 = v19;
      memmove((void *)(v17 + 340), v12, v19);
      v18 += v20;
    }
    if ( v14 )
    {
      v24 = *(unsigned __int16 *)v14;
      if ( (_WORD)v24 )
      {
        *(_DWORD *)(v17 + 332) = v24;
        memmove(v18, v14[1], *(unsigned __int16 *)v14);
        v18 += *(unsigned __int16 *)v14;
      }
    }
    if ( v13 )
    {
      v21 = *(unsigned __int16 *)v13;
      if ( (_WORD)v21 )
      {
        *(_DWORD *)(v17 + 336) = v21;
        memmove(v18, v13[1], *(unsigned __int16 *)v13);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_fa472c519fe6315f206bfef5f05c0219_Traceguids, v17);
    }
    *a8 = v17;
  }
  else
  {
    v11 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_fa472c519fe6315f206bfef5f05c0219_Traceguids, 3221225626LL);
    }
  }
  if ( v11 < 0 && v17 )
    RdbsspStatisticsEntryDeleteInstance(v17);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_fa472c519fe6315f206bfef5f05c0219_Traceguids, (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400760d0  mov     [rsp+arg_18], r9d
0x1400760d5  mov     [rsp+arg_10], r8d
0x1400760da  mov     [rsp+arg_8], rdx
0x1400760df  push    rbx
0x1400760e0  push    rsi
0x1400760e1  push    rdi
0x1400760e2  push    r12
0x1400760e4  push    r13
0x1400760e6  push    r14
0x1400760e8  push    r15
0x1400760ea  sub     rsp, 60h
0x1400760ee  mov     r10d, r8d
0x1400760f1  mov     r8, rdx
0x1400760f4  mov     rbx, rcx
0x1400760f7  mov     [rsp+98h+var_48], 0
0x140076100  xor     r15d, r15d
0x140076103  mov     [rsp+98h+var_54], r15d
0x140076108  lea     rdi, WPP_GLOBAL_Control
0x14007610f  mov     rcx, cs:WPP_GLOBAL_Control
0x140076116  cmp     rcx, rdi
0x140076119  jnz     loc_1400763B9
0x14007611f  mov     r12, [rsp+98h+Sid]
0x140076127  mov     rcx, cs:WPP_GLOBAL_Control
0x14007612e  cmp     rcx, rdi
0x140076131  jnz     loc_140076409
0x140076137  mov     r14, [rsp+98h+arg_30]
0x14007613f  mov     r13, [rsp+98h+arg_28]
0x140076147  mov     edi, 154h
0x14007614c  mov     [rsp+98h+var_58], edi
0x140076150  test    r12, r12
0x140076153  jnz     loc_1400762D4
0x140076159  test    r13, r13
0x14007615c  jnz     loc_1400762F0
0x140076162  test    r14, r14
0x140076165  jnz     loc_140076309
0x14007616b  mov     r8d, edi
0x14007616e  mov     rax, [rbx+10h]
0x140076172  mov     edx, 40h ; '@'
0x140076177  mov     r9d, 45536452h
0x14007617d  mov     rcx, rbx
0x140076180  call    _guard_dispatch_icall
0x140076185  mov     rsi, rax
0x140076188  mov     [rsp+98h+var_48], rax
0x14007618d  test    rax, rax
0x140076190  jz      loc_14007627B
0x140076196  lea     rdx, [rax+18h]
0x14007619a  mov     rax, [rbx+48h]
0x14007619e  mov     rcx, rbx
0x1400761a1  call    _guard_dispatch_icall
0x1400761a6  mov     [rsi], rbx
0x1400761a9  mov     rax, [rsp+98h+arg_8]
0x1400761b1  mov     [rsi+10h], rax
0x1400761b5  mov     dword ptr [rsi+20h], 1
0x1400761bc  mov     ecx, [rsp+98h+arg_10]
0x1400761c3  mov     [rsi+134h], ecx
0x1400761c9  mov     [rsi+138h], rax
0x1400761d0  mov     eax, [rsp+98h+arg_18]
0x1400761d7  mov     [rsi+144h], eax
0x1400761dd  lea     rbx, [rsi+154h]
0x1400761e4  mov     [rsp+98h+var_50], rbx
0x1400761e9  test    r12, r12
0x1400761ec  jz      short loc_14007621B
0x1400761ee  mov     rcx, r12; Sid
0x1400761f1  call    cs:__imp_RtlLengthSid
0x1400761f8  nop     dword ptr [rax+rax+00h]
0x1400761fd  mov     [rsi+148h], eax
0x140076203  mov     edi, eax
0x140076205  mov     r8d, eax; Size
0x140076208  mov     rdx, r12; Src
0x14007620b  mov     rcx, rbx; void *
0x14007620e  call    memmove
0x140076213  add     rbx, rdi
0x140076216  mov     [rsp+98h+var_50], rbx
0x14007621b  test    r13, r13
0x14007621e  jnz     loc_140076321
0x140076224  test    r14, r14
0x140076227  jz      short loc_140076254
0x140076229  movzx   eax, word ptr [r14]
0x14007622d  test    ax, ax
0x140076230  jz      short loc_140076254
0x140076232  mov     [rsi+150h], eax
0x140076238  movzx   r8d, word ptr [r14]; Size
0x14007623c  mov     rdx, [r14+8]; Src
0x140076240  mov     rcx, rbx; void *
0x140076243  call    memmove
0x140076248  movzx   eax, word ptr [r14]
0x14007624c  add     rbx, rax
0x14007624f  mov     [rsp+98h+var_50], rbx
0x140076254  mov     rcx, cs:WPP_GLOBAL_Control
0x14007625b  lea     rbx, WPP_GLOBAL_Control
0x140076262  cmp     rcx, rbx
0x140076265  jnz     loc_140076358
0x14007626b  mov     rax, [rsp+98h+arg_38]
0x140076273  mov     [rax], rsi
0x140076276  jmp     loc_14007638C
0x14007627b  mov     r15d, 0C000009Ah
0x140076281  mov     [rsp+98h+var_54], r15d
0x140076286  mov     rcx, cs:WPP_GLOBAL_Control
0x14007628d  lea     rbx, WPP_GLOBAL_Control
0x140076294  cmp     rcx, rbx
0x140076297  jz      loc_14007638C
0x14007629d  mov     eax, [rcx+2Ch]
0x1400762a0  bt      eax, 0Dh
0x1400762a4  jnb     loc_14007638C
0x1400762aa  cmp     byte ptr [rcx+29h], 4
0x1400762ae  jb      loc_14007638C
0x1400762b4  mov     edx, 15h
0x1400762b9  mov     r9d, 0C000009Ah
0x1400762bf  lea     r8, WPP_fa472c519fe6315f206bfef5f05c0219_Traceguids
0x1400762c6  mov     rcx, [rcx+18h]
0x1400762ca  call    WPP_SF_d
0x1400762cf  jmp     loc_14007638C
0x1400762d4  mov     rcx, r12; Sid
0x1400762d7  call    cs:__imp_RtlLengthSid
0x1400762de  nop     dword ptr [rax+rax+00h]
0x1400762e3  add     eax, edi
0x1400762e5  mov     edi, eax
0x1400762e7  mov     [rsp+98h+var_58], eax
0x1400762eb  jmp     loc_140076159
0x1400762f0  movzx   eax, word ptr [r13+0]
0x1400762f5  test    ax, ax
0x1400762f8  jz      loc_140076162
0x1400762fe  add     edi, eax
0x140076300  mov     [rsp+98h+var_58], edi
0x140076304  jmp     loc_140076162
0x140076309  movzx   eax, word ptr [r14]
0x14007630d  test    ax, ax
0x140076310  jz      loc_14007616B
0x140076316  add     edi, eax
0x140076318  mov     [rsp+98h+var_58], edi
0x14007631c  jmp     loc_14007616B
0x140076321  movzx   eax, word ptr [r13+0]
0x140076326  test    ax, ax
0x140076329  jz      loc_140076224
0x14007632f  mov     [rsi+14Ch], eax
0x140076335  movzx   r8d, word ptr [r13+0]; Size
0x14007633a  mov     rdx, [r13+8]; Src
0x14007633e  mov     rcx, rbx; void *
0x140076341  call    memmove
0x140076346  movzx   eax, word ptr [r13+0]
0x14007634b  add     rbx, rax
0x14007634e  mov     [rsp+98h+var_50], rbx
0x140076353  jmp     loc_140076224
0x140076358  test    dword ptr [rcx+2Ch], 2000h
0x14007635f  jz      loc_14007626B
0x140076365  cmp     byte ptr [rcx+29h], 4
0x140076369  jb      loc_14007626B
0x14007636f  mov     edx, 16h
0x140076374  mov     r9, rsi
0x140076377  lea     r8, WPP_fa472c519fe6315f206bfef5f05c0219_Traceguids
0x14007637e  mov     rcx, [rcx+18h]
0x140076382  call    WPP_SF_q
0x140076387  jmp     loc_14007626B
0x14007638c  test    r15d, r15d
0x14007638f  js      loc_140076453
0x140076395  mov     rcx, cs:WPP_GLOBAL_Control
0x14007639c  cmp     rcx, rbx
0x14007639f  jnz     loc_140076469
0x1400763a5  mov     eax, r15d
0x1400763a8  add     rsp, 60h
0x1400763ac  pop     r15
0x1400763ae  pop     r14
0x1400763b0  pop     r13
0x1400763b2  pop     r12
0x1400763b4  pop     rdi
0x1400763b5  pop     rsi
0x1400763b6  pop     rbx
0x1400763b7  retn
0x1400763b9  mov     eax, [rcx+2Ch]
0x1400763bc  bt      eax, 0Dh
0x1400763c0  jnb     loc_14007611F
0x1400763c6  cmp     byte ptr [rcx+29h], 4
0x1400763ca  jb      loc_14007611F
0x1400763d0  mov     edx, 13h
0x1400763d5  mov     r12, [rsp+98h+Sid]
0x1400763dd  mov     [rsp+98h+var_60], r12
0x1400763e2  mov     [rsp+98h+var_68], r9d
0x1400763e7  mov     dword ptr [rsp+98h+var_70], r10d
0x1400763ec  mov     [rsp+98h+var_78], r8
0x1400763f1  mov     r9, rbx
0x1400763f4  lea     r8, WPP_fa472c519fe6315f206bfef5f05c0219_Traceguids
0x1400763fb  mov     rcx, [rcx+18h]
0x1400763ff  call    WPP_SF_qqDDq
0x140076404  jmp     loc_140076127
0x140076409  mov     eax, [rcx+2Ch]
0x14007640c  bt      eax, 0Dh
0x140076410  jnb     loc_140076137
0x140076416  cmp     byte ptr [rcx+29h], 4
0x14007641a  jb      loc_140076137
0x140076420  mov     rax, [rsp+98h+arg_38]
0x140076428  mov     [rsp+98h+var_70], rax
0x14007642d  mov     r14, [rsp+98h+arg_30]
0x140076435  mov     [rsp+98h+var_78], r14
0x14007643a  mov     r13, [rsp+98h+arg_28]
0x140076442  mov     r9, r13
0x140076445  mov     rcx, [rcx+18h]
0x140076449  call    WPP_SF_ZZq
0x14007644e  jmp     loc_140076147
0x140076453  test    rsi, rsi
0x140076456  jz      loc_140076395
0x14007645c  mov     rcx, rsi
0x14007645f  call    RdbsspStatisticsEntryDeleteInstance
0x140076464  jmp     loc_140076395
0x140076469  test    dword ptr [rcx+2Ch], 2000h
0x140076470  jz      loc_1400763A5
0x140076476  cmp     byte ptr [rcx+29h], 4
0x14007647a  jb      loc_1400763A5
0x140076480  mov     edx, 17h
0x140076485  mov     r9d, r15d
0x140076488  lea     r8, WPP_fa472c519fe6315f206bfef5f05c0219_Traceguids
0x14007648f  mov     rcx, [rcx+18h]
0x140076493  call    WPP_SF_d
0x140076498  jmp     loc_1400763A5
0x14007b8a0  push    rbp
0x14007b8a2  sub     rsp, 40h
0x14007b8a6  mov     rbp, rdx
0x14007b8a9  cmp     dword ptr [rbp+44h], 0
0x14007b8ad  jge     short loc_14007B8C5
0x14007b8af  mov     rcx, [rbp+50h]
0x14007b8b3  test    rcx, rcx
0x14007b8b6  jz      short loc_14007B8C5
0x14007b8b8  call    RdbsspStatisticsEntryDeleteInstance
0x14007b8bd  mov     qword ptr [rbp+50h], 0
0x14007b8c5  add     rsp, 40h
0x14007b8c9  pop     rbp
0x14007b8ca  retn
```
