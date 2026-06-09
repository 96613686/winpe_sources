# CVoice::StopVoice(__int64)

- ea: `0x18000e3b0`
- end: `0x18000e4c6`
- name: `?StopVoice@CVoice@@QEAAX_J@Z`
- size: `278`
- prototype: `void(CVoice *__hidden this, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004120`
- `0x180006420`

## callees

- `0x18000b4b0`
- `0x18000e3b0`

## pseudocode

```c
void __fastcall CVoice::StopVoice(CVoice *this, __int64 a2)
{
  __int64 v2; // r11
  CVoice *v3; // r10
  __int64 v4; // rax
  int Level; // eax
  char *v6; // rdi
  bool v7; // zf

  v2 = a2;
  v3 = this;
  if ( *((_DWORD *)this + 137) )
  {
    v4 = *((_QWORD *)this + 65);
    if ( a2 <= v4 )
      v2 = v4 + 1;
    if ( *((_DWORD *)this + 40) )
    {
      Level = CVoiceEG::GetLevel((CVoice *)((char *)this + 88), v2, (__int64 *)this + 19, 1);
      *((_QWORD *)v3 + 13) = *((_QWORD *)v3 + 13) * Level / 1000LL;
    }
    v6 = (char *)v3 + 168;
    *((_QWORD *)v3 + 19) = v2;
    if ( *((_DWORD *)v3 + 60) )
      *((_QWORD *)v3 + 23) = *((_QWORD *)v3 + 23)
                           * (int)CVoiceEG::GetLevel((CVoice *)((char *)v3 + 168), v2, (__int64 *)v3 + 29, 1)
                           / 1000LL;
    *((_QWORD *)v6 + 8) = v2;
    v7 = *((_DWORD *)v3 + 217) == 1;
    *((_DWORD *)v3 + 137) = 0;
    *((_DWORD *)v3 + 140) = 0;
    *((_QWORD *)v3 + 66) = v2;
    *((_QWORD *)v3 + 67) = 0;
    if ( v7 )
      *((_DWORD *)v3 + 93) = 1;
  }
}

```

## disassembly

```asm
0x18000e3b0  sub     rsp, 28h
0x18000e3b4  cmp     dword ptr [rcx+224h], 0
0x18000e3bb  mov     r11, rdx
0x18000e3be  mov     r10, rcx
0x18000e3c1  jz      loc_18000E4C1
0x18000e3c7  mov     rax, [rcx+208h]
0x18000e3ce  mov     [rsp+28h+arg_0], rbx
0x18000e3d3  mov     [rsp+28h+arg_8], rsi
0x18000e3d8  mov     [rsp+28h+var_8], rdi
0x18000e3dd  cmp     rdx, rax
0x18000e3e0  jg      short loc_18000E3E6
0x18000e3e2  lea     r11, [rax+1]
0x18000e3e6  cmp     dword ptr [rcx+0A0h], 0
0x18000e3ed  mov     rsi, 20C49BA5E353F7CFh
0x18000e3f7  jz      short loc_18000E432
0x18000e3f9  lea     r8, [rcx+98h]; __int64 *
0x18000e400  mov     r9d, 1; int
0x18000e406  add     rcx, 58h ; 'X'; this
0x18000e40a  mov     rdx, r11; __int64
0x18000e40d  call    ?GetLevel@CVoiceEG@@AEAAJ_JPEA_JH@Z; CVoiceEG::GetLevel(__int64,__int64 *,int)
0x18000e412  movsxd  rcx, eax
0x18000e415  mov     rax, rsi
0x18000e418  imul    rcx, [r10+68h]
0x18000e41d  imul    rcx
0x18000e420  sar     rdx, 7
0x18000e424  mov     rax, rdx
0x18000e427  shr     rax, 3Fh
0x18000e42b  add     rdx, rax
0x18000e42e  mov     [r10+68h], rdx
0x18000e432  lea     rdi, [r10+0A8h]
0x18000e439  mov     [r10+98h], r11
0x18000e440  cmp     dword ptr [rdi+48h], 0
0x18000e444  jz      short loc_18000E47B
0x18000e446  mov     r9d, 1; int
0x18000e44c  lea     r8, [rdi+40h]; __int64 *
0x18000e450  mov     rdx, r11; __int64
0x18000e453  mov     rcx, rdi; this
0x18000e456  call    ?GetLevel@CVoiceEG@@AEAAJ_JPEA_JH@Z; CVoiceEG::GetLevel(__int64,__int64 *,int)
0x18000e45b  movsxd  rcx, eax
0x18000e45e  mov     rax, rsi
0x18000e461  imul    rcx, [rdi+10h]
0x18000e466  imul    rcx
0x18000e469  sar     rdx, 7
0x18000e46d  mov     rax, rdx
0x18000e470  shr     rax, 3Fh
0x18000e474  add     rdx, rax
0x18000e477  mov     [rdi+10h], rdx
0x18000e47b  mov     rsi, [rsp+28h+arg_8]
0x18000e480  xor     eax, eax
0x18000e482  mov     rbx, [rsp+28h+arg_0]
0x18000e487  mov     [rdi+40h], r11
0x18000e48b  cmp     dword ptr [r10+364h], 1
0x18000e493  mov     rdi, [rsp+28h+var_8]
0x18000e498  mov     [r10+224h], eax
0x18000e49f  mov     [r10+230h], eax
0x18000e4a6  mov     [r10+210h], r11
0x18000e4ad  mov     [r10+218h], rax
0x18000e4b4  jnz     short loc_18000E4C1
0x18000e4b6  mov     dword ptr [r10+174h], 1
0x18000e4c1  add     rsp, 28h
0x18000e4c5  retn
```
