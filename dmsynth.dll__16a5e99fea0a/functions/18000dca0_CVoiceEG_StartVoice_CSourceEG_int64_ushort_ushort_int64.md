# CVoiceEG::StartVoice(CSourceEG *,__int64,ushort,ushort,__int64)

- ea: `0x18000dca0`
- end: `0x18000dde4`
- name: `?StartVoice@CVoiceEG@@QEAA_JPEAVCSourceEG@@_JGG1@Z`
- size: `324`
- prototype: `__int64 __fastcall(CVoiceEG *__hidden this, struct CSourceEG *, __int64, unsigned __int16, unsigned __int16, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d3b0`
- `0x18000e040`

## callees

- `0x18000d0f0`
- `0x18000dca0`

## pseudocode

```c
__int64 __fastcall CVoiceEG::StartVoice(
        CVoiceEG *this,
        struct CSourceEG *a2,
        __int64 a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        __int64 a6)
{
  int v7; // edi
  int v8; // eax
  int v9; // r8d
  __int64 v10; // r11
  int v11; // eax
  __int64 v12; // r11
  __int64 v13; // r8
  __int128 v14; // rax
  __int64 result; // rax

  *((_DWORD *)this + 18) = 1;
  *((_QWORD *)this + 8) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)this + 7) = a3;
  v7 = a4;
  *(_OWORD *)this = *(_OWORD *)a2;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 2) = *((_OWORD *)a2 + 2);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 6);
  if ( *((_QWORD *)this + 2) < a6 )
    *((_QWORD *)this + 2) = a6;
  v8 = CDigitalAudio::PRELToPFRACT(a5 * *((__int16 *)this + 12) / 127);
  v9 = v7 * *((__int16 *)this + 13);
  *(_QWORD *)this = v10 * v8 / 4096;
  v11 = CDigitalAudio::PRELToPFRACT(v9 / 127);
  v13 = *((_QWORD *)this + 1) * v11;
  v14 = *((_QWORD *)this + 5) * v11;
  *(_QWORD *)&v14 = (WORD4(v14) & 0xFFF) + (_QWORD)v14;
  DWORD2(v14) = 1000 - *((__int16 *)this + 14);
  *((_QWORD *)this + 5) = (__int64)v14 >> 12;
  result = *((_QWORD *)this + 4);
  *((_QWORD *)this + 1) = v13 / 4096 * SDWORD2(v14) / 1000;
  if ( !result )
    return v12;
  return result;
}

```

## disassembly

```asm
0x18000dca0  mov     [rsp+arg_0], rbx
0x18000dca5  push    rdi
0x18000dca6  sub     rsp, 20h
0x18000dcaa  mov     dword ptr [rcx+48h], 1
0x18000dcb1  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000dcbb  mov     [rcx+40h], rax
0x18000dcbf  mov     rbx, rcx
0x18000dcc2  mov     rax, [rsp+28h+arg_28]
0x18000dcc7  mov     [rcx+38h], r8
0x18000dccb  movups  xmm0, xmmword ptr [rdx]
0x18000dcce  movzx   edi, r9w
0x18000dcd2  movups  xmmword ptr [rcx], xmm0
0x18000dcd5  movups  xmm1, xmmword ptr [rdx+10h]
0x18000dcd9  movups  xmmword ptr [rcx+10h], xmm1
0x18000dcdd  movups  xmm0, xmmword ptr [rdx+20h]
0x18000dce1  movups  xmmword ptr [rcx+20h], xmm0
0x18000dce5  movsd   xmm1, qword ptr [rdx+30h]
0x18000dcea  movsd   qword ptr [rcx+30h], xmm1
0x18000dcef  mov     r11, [rcx]
0x18000dcf2  cmp     r11, rax
0x18000dcf5  cmovl   r11, rax
0x18000dcf9  cmp     [rcx+10h], rax
0x18000dcfd  jge     short loc_18000DD03
0x18000dcff  mov     [rcx+10h], rax
0x18000dd03  movsx   r8d, word ptr [rcx+18h]
0x18000dd08  movzx   eax, [rsp+28h+arg_20]
0x18000dd0d  imul    r8d, eax
0x18000dd11  mov     eax, 81020409h
0x18000dd16  imul    r8d
0x18000dd19  add     edx, r8d
0x18000dd1c  sar     edx, 6
0x18000dd1f  mov     ecx, edx
0x18000dd21  shr     ecx, 1Fh
0x18000dd24  add     ecx, edx; int
0x18000dd26  call    ?PRELToPFRACT@CDigitalAudio@@SAJJ@Z; CDigitalAudio::PRELToPFRACT(long)
0x18000dd2b  movsx   r8d, word ptr [rbx+1Ah]
0x18000dd30  cdqe
0x18000dd32  imul    rax, r11
0x18000dd36  imul    r8d, edi
0x18000dd3a  cqo
0x18000dd3c  and     edx, 0FFFh
0x18000dd42  lea     r11, [rdx+rax]
0x18000dd46  mov     eax, 81020409h
0x18000dd4b  imul    r8d
0x18000dd4e  sar     r11, 0Ch
0x18000dd52  mov     [rbx], r11
0x18000dd55  lea     ecx, [r8+rdx]
0x18000dd59  sar     ecx, 6
0x18000dd5c  mov     edx, ecx
0x18000dd5e  shr     edx, 1Fh
0x18000dd61  add     ecx, edx; int
0x18000dd63  call    ?PRELToPFRACT@CDigitalAudio@@SAJJ@Z; CDigitalAudio::PRELToPFRACT(long)
0x18000dd68  movsx   ecx, word ptr [rbx+1Ch]
0x18000dd6c  movsxd  r8, eax
0x18000dd6f  mov     rax, r8
0x18000dd72  imul    rax, [rbx+28h]
0x18000dd77  imul    r8, [rbx+8]
0x18000dd7c  cqo
0x18000dd7e  and     edx, 0FFFh
0x18000dd84  add     rax, rdx
0x18000dd87  mov     edx, 3E8h
0x18000dd8c  sar     rax, 0Ch
0x18000dd90  sub     edx, ecx
0x18000dd92  mov     [rbx+28h], rax
0x18000dd96  movsxd  rcx, edx
0x18000dd99  mov     rax, r8
0x18000dd9c  cqo
0x18000dd9e  and     edx, 0FFFh
0x18000dda4  add     rax, rdx
0x18000dda7  sar     rax, 0Ch
0x18000ddab  imul    rcx, rax
0x18000ddaf  mov     rax, 20C49BA5E353F7CFh
0x18000ddb9  imul    rcx
0x18000ddbc  sar     rdx, 7
0x18000ddc0  mov     rax, rdx
0x18000ddc3  shr     rax, 3Fh
0x18000ddc7  add     rdx, rax
0x18000ddca  mov     rax, [rbx+20h]
0x18000ddce  test    rax, rax
0x18000ddd1  mov     [rbx+8], rdx
0x18000ddd5  mov     rbx, [rsp+28h+arg_0]
0x18000ddda  cmovz   rax, r11
0x18000ddde  add     rsp, 20h
0x18000dde2  pop     rdi
0x18000dde3  retn
```
