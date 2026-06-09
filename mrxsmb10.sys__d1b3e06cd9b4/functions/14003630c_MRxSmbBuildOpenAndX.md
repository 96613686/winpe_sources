# MRxSmbBuildOpenAndX

- ea: `0x14003630c`
- end: `0x140036524`
- name: `MRxSmbBuildOpenAndX`
- size: `536`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140047fb0`

## callees

- `0x14000dfa8`
- `0x14003630c`
- `0x14003b2d4`
- `0x14003b320`
- `0x14003b370`
- `0x14003b8d4`
- `0x140044700`
- `0x140046380`
- `0x14004a590`
- `0x1400526a4`

## pseudocode

```c
__int64 __fastcall MRxSmbBuildOpenAndX(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rsi
  unsigned int v5; // ebp
  int v6; // r13d
  __int16 v7; // ax
  __int64 v8; // r11
  __int16 v9; // r10
  unsigned __int16 v10; // r10
  unsigned __int16 v11; // r15
  unsigned int started; // r14d
  __int64 v13; // r9
  __int64 v15; // [rsp+20h] [rbp-78h]
  __int64 v16; // [rsp+20h] [rbp-78h]
  __int64 v17; // [rsp+20h] [rbp-78h]
  int v18; // [rsp+28h] [rbp-70h]
  __int64 v19; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v20; // [rsp+B0h] [rbp+18h] BYREF

  v19 = a2;
  v2 = *(_QWORD *)(a1 + 48);
  v4 = *(_QWORD *)(v2 + 56) + 360LL;
  v20 = 0;
  LODWORD(v19) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  v5 = 1;
  if ( !MRxSmbOplocksDisabled && !(unsigned __int8)MRxSmbIsStreamFile(v4, 0) )
  {
    *(_DWORD *)(v2 + 732) = 31;
    v5 = 7;
  }
  MRxSmbMapDisposition(*(unsigned int *)(v2 + 536));
  v6 = (unsigned __int16)MRxSmbMapFileAttributes(*(unsigned int *)(v2 + 528));
  MRxSmbMapShareAccess(*(unsigned __int16 *)(v2 + 532));
  v7 = MRxSmbMapDesiredAccess(*(unsigned int *)(v2 + 512));
  v10 = v7 | v9;
  v11 = v10 | 0x4000;
  if ( (*(_BYTE *)(v2 + 540) & 2) == 0 )
    v11 = v10;
  if ( (*(_DWORD *)(v8 + 420) & 0x20) != 0 )
  {
    v20 = MEMORY[0xFFFFF78000000014];
    MRxSmbTimeToSecondsSince1970(&v20, v8 + 400, &v19);
  }
  else
  {
    LODWORD(v19) = 0;
  }
  started = MRxSmbStartSMBCommand(a1, 2, 45, 33, v15, 0x40000u);
  if ( !started )
  {
    LODWORD(v16) = 22;
    MRxSmbStuffSMB(a1, "XwwwwdwDddB", v5, v11, v16, v6);
    if ( *(_BYTE *)(*(_QWORD *)(v2 + 648) + 77LL) == 1 )
      MRxSmbStuffSMB(a1, "z>!", &MRxSmbOpenAndX_PipeString, v4, v17, v18);
    else
      MRxSmbStuffSMB(a1, "z!", v4, v13, v17, v18);
  }
  return started;
}

```

## disassembly

```asm
0x14003630c  mov     rax, rsp
0x14003630f  mov     [rax+20h], rbx
0x140036313  mov     [rax+10h], rdx
0x140036317  push    rbp
0x140036318  push    rsi
0x140036319  push    rdi
0x14003631a  push    r12
0x14003631c  push    r13
0x14003631e  push    r14
0x140036320  push    r15
0x140036322  sub     rsp, 60h
0x140036326  mov     rdi, [rcx+30h]
0x14003632a  mov     rbx, rcx
0x14003632d  mov     r14, [rcx+38h]
0x140036331  mov     rsi, [rdi+38h]
0x140036335  add     rsi, 168h
0x14003633c  xor     r15d, r15d
0x14003633f  mov     [rax+18h], r15
0x140036343  mov     [rax+10h], r15d
0x140036347  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003634e  lea     rax, WPP_GLOBAL_Control
0x140036355  cmp     rcx, rax
0x140036358  jz      short loc_140036377
0x14003635a  test    dword ptr [rcx+2Ch], 400h
0x140036361  jz      short loc_140036377
0x140036363  mov     rcx, [rcx+18h]
0x140036367  lea     edx, [r15+22h]
0x14003636b  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036372  call    WPP_SF_
0x140036377  cmp     cs:MRxSmbOplocksDisabled, r15b
0x14003637e  mov     eax, 1
0x140036383  mov     ebp, eax
0x140036385  jnz     short loc_1400363A4
0x140036387  xor     edx, edx
0x140036389  mov     rcx, rsi
0x14003638c  call    MRxSmbIsStreamFile
0x140036391  test    al, al
0x140036393  jnz     short loc_1400363A4
0x140036395  mov     dword ptr [rdi+2DCh], 1Fh
0x14003639f  mov     ebp, 7
0x1400363a4  mov     ecx, [rdi+218h]
0x1400363aa  mov     r11, [r14+50h]
0x1400363ae  call    MRxSmbMapDisposition
0x1400363b3  mov     ecx, [rdi+210h]
0x1400363b9  movzx   r12d, ax
0x1400363bd  call    MRxSmbMapFileAttributes
0x1400363c2  movzx   ecx, word ptr [rdi+214h]
0x1400363c9  movzx   r13d, ax
0x1400363cd  mov     eax, [rdi+208h]
0x1400363d3  mov     [rsp+98h+arg_0], eax
0x1400363da  call    MRxSmbMapShareAccess
0x1400363df  mov     ecx, [rdi+200h]
0x1400363e5  movzx   r10d, ax
0x1400363e9  call    MRxSmbMapDesiredAccess
0x1400363ee  or      r10w, ax
0x1400363f2  mov     eax, [r11+1A4h]
0x1400363f9  movzx   r15d, r10w
0x1400363fd  or      r15w, 4000h
0x140036403  test    byte ptr [rdi+21Ch], 2
0x14003640a  cmovz   r15w, r10w
0x14003640f  test    al, 20h
0x140036411  jz      short loc_140036446
0x140036413  mov     rax, 0FFFFF78000000014h
0x14003641d  lea     r8, [rsp+98h+arg_8]
0x140036425  lea     rdx, [r11+190h]
0x14003642c  lea     rcx, [rsp+98h+arg_10]
0x140036434  mov     rax, [rax]
0x140036437  mov     [rsp+98h+arg_10], rax
0x14003643f  call    MRxSmbTimeToSecondsSince1970
0x140036444  jmp     short loc_140036451
0x140036446  mov     dword ptr [rsp+98h+arg_8], 0
0x140036451  mov     r9d, 21h ; '!'
0x140036457  mov     [rsp+98h+var_70], 40000h
0x14003645f  mov     r8b, 2Dh ; '-'
0x140036462  mov     rcx, rbx
0x140036465  lea     edx, [r9-1Fh]
0x140036469  call    MRxSmbStartSMBCommand
0x14003646e  mov     r14d, eax
0x140036471  test    eax, eax
0x140036473  jnz     loc_140036508
0x140036479  mov     ecx, dword ptr [rsp+98h+arg_8]
0x140036480  lea     rdx, aXwwwwdwdddb; "XwwwwdwDddB"
0x140036487  mov     eax, [rsp+98h+arg_0]
0x14003648e  mov     r8d, ebp
0x140036491  mov     [rsp+98h+var_40], 0
0x14003649a  mov     [rsp+98h+var_48], 0
0x1400364a3  mov     [rsp+98h+var_50], 0FFFFFFFFh
0x1400364ab  mov     [rsp+98h+var_58], eax
0x1400364af  mov     [rsp+98h+var_60], r12d
0x1400364b4  mov     [rsp+98h+var_68], ecx
0x1400364b8  mov     rcx, rbx
0x1400364bb  mov     [rsp+98h+var_70], r13d
0x1400364c0  movzx   r9d, r15w
0x1400364c4  mov     dword ptr [rsp+98h+var_78], 16h
0x1400364cc  call    MRxSmbStuffSMB
0x1400364d1  mov     rax, [rdi+288h]
0x1400364d8  mov     rcx, rbx
0x1400364db  cmp     byte ptr [rax+4Dh], 1
0x1400364df  jnz     short loc_1400364F9
0x1400364e1  mov     r9, rsi
0x1400364e4  lea     r8, MRxSmbOpenAndX_PipeString
0x1400364eb  lea     rdx, aZ_0; "z>!"
0x1400364f2  call    MRxSmbStuffSMB
0x1400364f7  jmp     short loc_140036508
0x1400364f9  mov     r8, rsi
0x1400364fc  lea     rdx, aZ; "z!"
0x140036503  call    MRxSmbStuffSMB
0x140036508  mov     rbx, [rsp+98h+arg_18]
0x140036510  mov     eax, r14d
0x140036513  add     rsp, 60h
0x140036517  pop     r15
0x140036519  pop     r14
0x14003651b  pop     r13
0x14003651d  pop     r12
0x14003651f  pop     rdi
0x140036520  pop     rsi
0x140036521  pop     rbp
0x140036522  retn
```
