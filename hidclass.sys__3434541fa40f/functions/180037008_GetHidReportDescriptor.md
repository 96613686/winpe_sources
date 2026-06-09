# GetHidReportDescriptor

- ea: `0x180037008`
- end: `0x18003737e`
- name: `GetHidReportDescriptor`
- size: `886`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003d8fc`

## callees

- `0x180008650`
- `0x18000ddc8`
- `0x180014e80`
- `0x1800227cc`
- `0x180037008`
- `0x18003de60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180037259`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037259`
- `ntoskrnl!ExAllocatePool2` at `0x18003703e`
- `ntoskrnl!ExAllocatePool2` at `0x18003703e`

## pseudocode

```c
__int64 __fastcall GetHidReportDescriptor(__int64 *a1, _QWORD *a2, __int64 a3)
{
  __int64 v3; // r12
  void *Pool2; // r13
  unsigned int v6; // edi
  unsigned int v7; // eax
  char v8; // bl
  __int64 v9; // rax
  int v10; // edx
  __int64 v11; // r9
  PDEVICE_OBJECT v12; // rcx
  bool v13; // bl
  int v15; // [rsp+20h] [rbp-88h]
  int v16; // [rsp+28h] [rbp-80h]
  int v17; // [rsp+30h] [rbp-78h]
  __int16 v18; // [rsp+30h] [rbp-78h]
  int v19; // [rsp+38h] [rbp-70h]
  __int64 v20; // [rsp+40h] [rbp-68h]
  char v21; // [rsp+48h] [rbp-60h]
  _QWORD *v22; // [rsp+B8h] [rbp+10h]
  unsigned int v23; // [rsp+C0h] [rbp+18h]

  v22 = a2;
  v3 = (unsigned int)a3;
  if ( !(_DWORD)a3 )
  {
    v6 = -1073741668;
    v12 = WPP_GLOBAL_Control;
    v13 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v21 = -100;
    v20 = *a1;
    v18 = 14;
LABEL_51:
    LOBYTE(a2) = v13;
    WPP_RECORDER_AND_TRACE_SF_qL(
      v12->AttachedDevice,
      (_DWORD)a2,
      a3,
      a1[84],
      3,
      2,
      v18,
      (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
      v20,
      v21);
    return v6;
  }
  Pool2 = (void *)ExAllocatePool2(64, (unsigned int)a3, 1130654024);
  if ( !Pool2 )
  {
    v6 = -1073741670;
    v12 = WPP_GLOBAL_Control;
    v13 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v6;
    v21 = -102;
    v20 = *a1;
    v18 = 13;
    goto LABEL_51;
  }
  v6 = 0;
  v7 = 0;
  v8 = 1;
  while ( 1 )
  {
    v23 = v7;
    if ( v7 >= 3 )
      break;
    v9 = v22[23];
    v22[14] = Pool2;
    *(_BYTE *)(v9 - 72) = 15;
    *(_DWORD *)(v9 - 64) = v3;
    *(_DWORD *)(v9 - 48) = 720903;
    v6 = HidpCallDriverSynchronous(*a1, v22, a3);
    if ( (v6 & 0x80000000) != 0 )
    {
      LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qLL(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)a2,
          a3,
          a1[84],
          3,
          2,
          11,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          *a1,
          v23,
          v6);
    }
    else
    {
      v10 = (int)v22;
      v11 = v22[7];
      if ( v11 == v3 )
      {
        *((_DWORD *)a1 + 36) = v3;
        a1[17] = (__int64)Pool2;
        return v6;
      }
      v6 = -1073741668;
      LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdiDd(
          WPP_GLOBAL_Control->AttachedDevice,
          v10,
          a3,
          a1[84],
          v15,
          v16,
          v17,
          v19,
          *a1,
          v23,
          v11,
          v3);
      }
      TraceLoggingIrpIoctlFailed(a1, 720903, "Returned length does not match", v11);
    }
    v7 = v23 + 1;
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v8 = 0;
    }
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = v8;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)a2,
        a3,
        a1[84],
        3,
        2,
        12,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *a1,
        3);
    }
    ExFreePoolWithTag(Pool2, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x180037008  mov     [rsp+arg_0], rbx
0x18003700d  mov     [rsp+arg_8], rdx
0x180037012  push    rbp
0x180037013  push    rsi
0x180037014  push    rdi
0x180037015  push    r12
0x180037017  push    r13
0x180037019  push    r14
0x18003701b  push    r15
0x18003701d  sub     rsp, 70h
0x180037021  mov     r12d, r8d
0x180037024  mov     rsi, rcx
0x180037027  test    r8d, r8d
0x18003702a  jz      loc_1800372DC
0x180037030  mov     edx, r12d
0x180037033  mov     ecx, 40h ; '@'
0x180037038  mov     r8d, 43646948h
0x18003703e  call    cs:__imp_ExAllocatePool2
0x180037045  nop     dword ptr [rax+rax+00h]
0x18003704a  mov     r13, rax
0x18003704d  test    rax, rax
0x180037050  jz      loc_18003726A
0x180037056  xor     edi, edi
0x180037058  lea     r14, WPP_GLOBAL_Control
0x18003705f  xor     eax, eax
0x180037061  lea     r15, WPP_RECORDER_INITIALIZED
0x180037068  lea     ebp, [rdi+2]
0x18003706b  lea     ebx, [rdi+1]
0x18003706e  mov     [rsp+0A8h+arg_10], eax
0x180037075  cmp     eax, 3
0x180037078  jnb     loc_1800371DE
0x18003707e  mov     rcx, [rsp+0A8h+arg_8]
0x180037086  mov     rdx, rcx
0x180037089  mov     rax, [rcx+0B8h]
0x180037090  mov     [rcx+70h], r13
0x180037094  mov     byte ptr [rax-48h], 0Fh
0x180037098  mov     [rax-40h], r12d
0x18003709c  mov     dword ptr [rax-30h], 0B0007h
0x1800370a3  mov     rcx, [rsi]
0x1800370a6  call    HidpCallDriverSynchronous
0x1800370ab  mov     edi, eax
0x1800370ad  test    eax, eax
0x1800370af  js      loc_180037146
0x1800370b5  mov     rdx, [rsp+0A8h+arg_8]
0x1800370bd  mov     r9, [rdx+38h]
0x1800370c1  cmp     r9, r12
0x1800370c4  jz      loc_1800371CB
0x1800370ca  mov     edi, 0C000009Ch
0x1800370cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370d6  cmp     rcx, r14
0x1800370d9  jz      short loc_1800370ED
0x1800370db  mov     eax, [rcx+2Ch]
0x1800370de  test    bpl, al
0x1800370e1  jz      short loc_1800370ED
0x1800370e3  cmp     byte ptr [rcx+29h], 3
0x1800370e7  jb      short loc_1800370ED
0x1800370e9  mov     dl, bl
0x1800370eb  jmp     short loc_1800370EF
0x1800370ed  xor     dl, dl
0x1800370ef  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800370f6  setnz   r8b
0x1800370fa  test    dl, dl
0x1800370fc  jnz     short loc_180037103
0x1800370fe  test    r8b, r8b
0x180037101  jz      short loc_180037130
0x180037103  mov     eax, [rsp+0A8h+arg_10]
0x18003710a  mov     rcx, [rcx+18h]
0x18003710e  mov     [rsp+0A8h+var_50], r12d
0x180037113  mov     [rsp+0A8h+var_58], r9
0x180037118  mov     r9, [rsi+2A0h]
0x18003711f  mov     dword ptr [rsp+0A8h+var_60], eax
0x180037123  mov     rax, [rsi]
0x180037126  mov     [rsp+0A8h+var_68], rax
0x18003712b  call    WPP_RECORDER_AND_TRACE_SF_qdiDd
0x180037130  lea     r8, aReturnedLength; "Returned length does not match"
0x180037137  mov     edx, 0B0007h
0x18003713c  mov     rcx, rsi
0x18003713f  call    TraceLoggingIrpIoctlFailed
0x180037144  jmp     short loc_1800371BD
0x180037146  mov     rcx, cs:WPP_GLOBAL_Control
0x18003714d  cmp     rcx, r14
0x180037150  jz      short loc_180037164
0x180037152  mov     eax, [rcx+2Ch]
0x180037155  test    bpl, al
0x180037158  jz      short loc_180037164
0x18003715a  cmp     byte ptr [rcx+29h], 3
0x18003715e  jb      short loc_180037164
0x180037160  mov     dl, bl
0x180037162  jmp     short loc_180037166
0x180037164  xor     dl, dl
0x180037166  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003716d  setnz   r8b
0x180037171  test    dl, dl
0x180037173  jnz     short loc_18003717A
0x180037175  test    r8b, r8b
0x180037178  jz      short loc_1800371BD
0x18003717a  mov     eax, [rsp+0A8h+arg_10]
0x180037181  mov     r9, [rsi+2A0h]
0x180037188  mov     rcx, [rcx+18h]
0x18003718c  mov     dword ptr [rsp+0A8h+var_58], edi
0x180037190  mov     dword ptr [rsp+0A8h+var_60], eax
0x180037194  mov     rax, [rsi]
0x180037197  mov     [rsp+0A8h+var_68], rax
0x18003719c  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x1800371a3  mov     [rsp+0A8h+var_70], rax
0x1800371a8  mov     [rsp+0A8h+var_78], 0Bh
0x1800371af  mov     [rsp+0A8h+var_80], ebp
0x1800371b3  mov     [rsp+0A8h+var_88], 3
0x1800371b8  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x1800371bd  mov     eax, [rsp+0A8h+arg_10]
0x1800371c4  add     eax, ebx
0x1800371c6  jmp     loc_18003706E
0x1800371cb  mov     [rsi+90h], r12d
0x1800371d2  mov     [rsi+88h], r13
0x1800371d9  jmp     loc_180037363
0x1800371de  test    edi, edi
0x1800371e0  jns     loc_180037363
0x1800371e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371ed  cmp     rcx, r14
0x1800371f0  jz      short loc_180037200
0x1800371f2  mov     eax, [rcx+2Ch]
0x1800371f5  test    bpl, al
0x1800371f8  jz      short loc_180037200
0x1800371fa  cmp     byte ptr [rcx+29h], 3
0x1800371fe  jnb     short loc_180037202
0x180037200  xor     bl, bl
0x180037202  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180037209  setnz   r8b
0x18003720d  test    bl, bl
0x18003720f  jnz     short loc_180037216
0x180037211  test    r8b, r8b
0x180037214  jz      short loc_180037254
0x180037216  mov     rax, [rsi]
0x180037219  mov     dl, bl
0x18003721b  mov     r9, [rsi+2A0h]
0x180037222  mov     rcx, [rcx+18h]
0x180037226  mov     dword ptr [rsp+0A8h+var_60], 3
0x18003722e  mov     [rsp+0A8h+var_68], rax
0x180037233  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18003723a  mov     [rsp+0A8h+var_70], rax
0x18003723f  mov     [rsp+0A8h+var_78], 0Ch
0x180037246  mov     [rsp+0A8h+var_80], ebp
0x18003724a  mov     [rsp+0A8h+var_88], 3
0x18003724f  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180037254  xor     edx, edx; Tag
0x180037256  mov     rcx, r13; P
0x180037259  call    cs:__imp_ExFreePoolWithTag
0x180037260  nop     dword ptr [rax+rax+00h]
0x180037265  jmp     loc_180037363
0x18003726a  mov     edi, 0C000009Ah
0x18003726f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037276  lea     r14, WPP_GLOBAL_Control
0x18003727d  mov     ebp, 2
0x180037282  cmp     rcx, r14
0x180037285  jz      short loc_18003729A
0x180037287  mov     eax, [rcx+2Ch]
0x18003728a  test    bpl, al
0x18003728d  jz      short loc_18003729A
0x18003728f  cmp     byte ptr [rcx+29h], 3
0x180037293  jb      short loc_18003729A
0x180037295  lea     ebx, [rbp-1]
0x180037298  jmp     short loc_18003729C
0x18003729a  xor     bl, bl
0x18003729c  lea     r15, WPP_RECORDER_INITIALIZED
0x1800372a3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800372aa  setnz   r8b
0x1800372ae  test    bl, bl
0x1800372b0  jnz     short loc_1800372BB
0x1800372b2  test    r8b, r8b
0x1800372b5  jz      loc_180037363
0x1800372bb  mov     rax, [rsi]
0x1800372be  mov     dword ptr [rsp+0A8h+var_60], edi
0x1800372c2  mov     [rsp+0A8h+var_68], rax
0x1800372c7  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x1800372ce  mov     [rsp+0A8h+var_70], rax
0x1800372d3  mov     [rsp+0A8h+var_78], 0Dh
0x1800372da  jmp     short loc_180037348
0x1800372dc  mov     edi, 0C000009Ch
0x1800372e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372e8  lea     r14, WPP_GLOBAL_Control
0x1800372ef  mov     ebp, 2
0x1800372f4  cmp     rcx, r14
0x1800372f7  jz      short loc_18003730C
0x1800372f9  mov     eax, [rcx+2Ch]
0x1800372fc  test    bpl, al
0x1800372ff  jz      short loc_18003730C
0x180037301  cmp     byte ptr [rcx+29h], 3
0x180037305  jb      short loc_18003730C
0x180037307  lea     ebx, [rbp-1]
0x18003730a  jmp     short loc_18003730E
0x18003730c  xor     bl, bl
0x18003730e  lea     r15, WPP_RECORDER_INITIALIZED
0x180037315  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003731c  setnz   r8b
0x180037320  test    bl, bl
0x180037322  jnz     short loc_180037329
0x180037324  test    r8b, r8b
0x180037327  jz      short loc_180037363
0x180037329  mov     rax, [rsi]
0x18003732c  mov     dword ptr [rsp+0A8h+var_60], edi
0x180037330  mov     [rsp+0A8h+var_68], rax
0x180037335  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18003733c  mov     [rsp+0A8h+var_70], rax
0x180037341  mov     [rsp+0A8h+var_78], 0Eh
0x180037348  mov     r9, [rsi+2A0h]
0x18003734f  mov     dl, bl
0x180037351  mov     rcx, [rcx+18h]
0x180037355  mov     [rsp+0A8h+var_80], ebp
0x180037359  mov     [rsp+0A8h+var_88], 3
0x18003735e  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180037363  mov     rbx, [rsp+0A8h+arg_0]
0x18003736b  mov     eax, edi
0x18003736d  add     rsp, 70h
0x180037371  pop     r15
0x180037373  pop     r14
0x180037375  pop     r13
0x180037377  pop     r12
0x180037379  pop     rdi
0x18003737a  pop     rsi
0x18003737b  pop     rbp
0x18003737c  retn
```
