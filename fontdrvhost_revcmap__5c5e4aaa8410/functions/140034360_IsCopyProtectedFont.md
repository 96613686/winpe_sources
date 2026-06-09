# IsCopyProtectedFont

- ea: `0x140034360`
- end: `0x14003446f`
- name: `IsCopyProtectedFont`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140033950`

## callees

- `0x140034360`
- `0x1400344ac`
- `0x140075de0`

## pseudocode

```c
__int64 __fastcall IsCopyProtectedFont(__int64 a1, int a2, char a3, char a4, char a5, _BYTE *a6)
{
  unsigned int v6; // ebx
  int v7; // eax
  _OWORD v9[7]; // [rsp+20h] [rbp-B8h] BYREF
  _QWORD v10[6]; // [rsp+90h] [rbp-48h] BYREF

  v6 = 1;
  v9[0] = *(_OWORD *)faCallbacks;
  v9[1] = *(_OWORD *)off_140099A20;
  v9[2] = *(_OWORD *)off_140099A30;
  v9[3] = *(_OWORD *)&off_140099A40;
  v9[4] = *(_OWORD *)&off_140099A50;
  v9[5] = *(_OWORD *)off_140099A60;
  v9[6] = *(_OWORD *)off_140099A70;
  memset(v10, 0, sizeof(v10));
  if ( !a1 || !a2 || !a6 )
    return 0;
  *a6 = 0;
  if ( a3 == 4 && a4 )
  {
    *(_QWORD *)&v9[0] = v10;
    v10[0] = a1;
    LODWORD(v10[1]) = a2;
    v7 = ((__int64 (__fastcall *)(_QWORD, _OWORD *, __int64, _QWORD))fa_VerifyFontLicensing)(0, v9, a1, 0);
    if ( !v7 )
    {
      *a6 = 1;
      return v6;
    }
    if ( v7 != -4 || a5 == 13 )
      return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x140034360  mov     r11, rsp
0x140034363  mov     [r11+8], rbx
0x140034367  push    rdi
0x140034368  sub     rsp, 0D0h
0x14003436f  mov     rax, cs:__security_cookie
0x140034376  xor     rax, rsp
0x140034379  mov     [rsp+0D8h+var_18], rax
0x140034381  mov     rdi, [rsp+0D8h+arg_28]
0x140034389  mov     ebx, 1
0x14003438e  movaps  xmm0, xmmword ptr cs:faCallbacks
0x140034395  movaps  [rsp+0D8h+var_B8], xmm0
0x14003439a  movaps  xmm1, xmmword ptr cs:off_140099A20
0x1400343a1  movaps  [rsp+0D8h+var_A8], xmm1
0x1400343a6  movaps  xmm0, xmmword ptr cs:off_140099A30
0x1400343ad  movaps  [rsp+0D8h+var_98], xmm0
0x1400343b2  movaps  xmm1, xmmword ptr cs:off_140099A40
0x1400343b9  movaps  [rsp+0D8h+var_88], xmm1
0x1400343be  movaps  xmm0, xmmword ptr cs:off_140099A50
0x1400343c5  movaps  [rsp+0D8h+var_78], xmm0
0x1400343ca  movaps  xmm1, xmmword ptr cs:off_140099A60
0x1400343d1  movaps  [rsp+0D8h+var_68], xmm1
0x1400343d6  movaps  xmm0, xmmword ptr cs:off_140099A70
0x1400343dd  movaps  xmmword ptr [r11-58h], xmm0
0x1400343e2  xorps   xmm1, xmm1
0x1400343e5  movups  xmmword ptr [r11-48h], xmm1
0x1400343ea  movups  xmmword ptr [r11-38h], xmm1
0x1400343ef  movups  xmmword ptr [r11-28h], xmm1
0x1400343f4  test    rcx, rcx
0x1400343f7  jz      short loc_14003444A
0x1400343f9  test    edx, edx
0x1400343fb  jz      short loc_14003444A
0x1400343fd  test    rdi, rdi
0x140034400  jz      short loc_14003444A
0x140034402  mov     byte ptr [rdi], 0
0x140034405  cmp     r8b, 4
0x140034409  jnz     short loc_14003444C
0x14003440b  test    r9b, r9b
0x14003440e  jz      short loc_14003444C
0x140034410  lea     rax, [r11-48h]
0x140034414  mov     qword ptr [rsp+0D8h+var_B8], rax
0x140034419  mov     [r11-48h], rcx
0x14003441d  mov     [r11-40h], edx
0x140034421  xor     r9d, r9d
0x140034424  mov     r8, rcx
0x140034427  lea     rdx, [rsp+0D8h+var_B8]
0x14003442c  xor     ecx, ecx
0x14003442e  call    fa_VerifyFontLicensing
0x140034433  test    eax, eax
0x140034435  jnz     short loc_14003443B
0x140034437  mov     [rdi], bl
0x140034439  jmp     short loc_14003444C
0x14003443b  cmp     eax, 0FFFFFFFCh
0x14003443e  jnz     short loc_14003444A
0x140034440  cmp     [rsp+0D8h+arg_20], 0Dh
0x140034448  jnz     short loc_14003444C
0x14003444a  xor     ebx, ebx
0x14003444c  mov     eax, ebx
0x14003444e  mov     rcx, [rsp+0D8h+var_18]
0x140034456  xor     rcx, rsp; StackCookie
0x140034459  call    __security_check_cookie
0x14003445e  mov     rbx, [rsp+0D8h+arg_0]
0x140034466  add     rsp, 0D0h
0x14003446d  pop     rdi
0x14003446e  retn
0x1400967cd  push    rbp
0x1400967cf  sub     rsp, 20h
0x1400967d3  mov     rbp, rdx
0x1400967d6  add     rsp, 20h
0x1400967da  pop     rbp
0x1400967db  retn
```
