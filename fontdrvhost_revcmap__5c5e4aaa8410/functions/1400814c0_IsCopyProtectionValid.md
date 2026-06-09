# IsCopyProtectionValid

- ea: `0x1400814c0`
- end: `0x1400816a6`
- name: `IsCopyProtectionValid`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140033950`

## callees

- `0x1400344ac`
- `0x140075de0`
- `0x140080f78`
- `0x1400814c0`

## pseudocode

```c
__int64 __fastcall IsCopyProtectionValid(
        __int64 a1,
        int a2,
        __int64 a3,
        bool *a4,
        bool *a5,
        _WORD *a6,
        _WORD *a7,
        _BYTE *a8)
{
  unsigned int v9; // ebx
  int v10; // ecx
  __int128 v12; // [rsp+20h] [rbp-F8h] BYREF
  __int64 v13; // [rsp+30h] [rbp-E8h]
  _OWORD v14[7]; // [rsp+40h] [rbp-D8h] BYREF
  __int128 v15; // [rsp+B0h] [rbp-68h] BYREF
  __int128 v16; // [rsp+C0h] [rbp-58h] BYREF
  __int128 v17; // [rsp+D0h] [rbp-48h]

  v9 = 0;
  v14[0] = *(_OWORD *)faCallbacks;
  v14[1] = *(_OWORD *)off_140099A20;
  v14[2] = *(_OWORD *)off_140099A30;
  v14[3] = *(_OWORD *)&off_140099A40;
  v14[4] = *(_OWORD *)&off_140099A50;
  v14[5] = *(_OWORD *)off_140099A60;
  v14[6] = *(_OWORD *)off_140099A70;
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  if ( a1 && a2 && a4 && a6 && a5 && a8 )
  {
    *a8 = 0;
    *(_QWORD *)&v14[0] = &v15;
    *(_QWORD *)&v15 = a1;
    DWORD2(v15) = a2;
    v10 = ((__int64 (__fastcall *)(__int64, _OWORD *, __int64, __int128 *))fa_VerifyFontLicensing)(2, v14, a1, &v12);
    if ( ((v10 + 14) & 0xFFFFFFFA) == 0 && v10 != -13 )
      goto LABEL_13;
    if ( !v10 )
    {
      *a4 = WORD4(v12) != 0;
      *a6 = WORD3(v12);
      *a7 = BYTE6(v13);
      *a5 = HIBYTE(v13) == 0;
      if ( !BYTE5(v13) || !(unsigned int)fa_VerifyFontLicensing(1, v14, v15, 0, v12) )
      {
        *a8 = 1;
LABEL_13:
        v9 = 1;
      }
    }
  }
  EnhancedUnmapRW((char *)&v16 + 8, *((_QWORD *)&v17 + 1), (unsigned int)v17);
  return v9;
}

```

## disassembly

```asm
0x1400814c0  mov     r11, rsp
0x1400814c3  mov     [r11+8], rbx
0x1400814c7  mov     [r11+10h], rsi
0x1400814cb  push    rdi
0x1400814cc  push    r12
0x1400814ce  push    r13
0x1400814d0  push    r14
0x1400814d2  push    r15
0x1400814d4  sub     rsp, 0F0h
0x1400814db  mov     rax, cs:__security_cookie
0x1400814e2  xor     rax, rsp
0x1400814e5  mov     [rsp+118h+var_38], rax
0x1400814ed  mov     rsi, r9
0x1400814f0  mov     r14, [rsp+118h+arg_20]
0x1400814f8  mov     r15, [rsp+118h+arg_28]
0x140081500  mov     r12, [rsp+118h+arg_30]
0x140081508  mov     rdi, [rsp+118h+arg_38]
0x140081510  xor     r13d, r13d
0x140081513  mov     ebx, r13d
0x140081516  movaps  xmm0, xmmword ptr cs:faCallbacks
0x14008151d  movaps  [rsp+118h+var_D8], xmm0
0x140081522  movaps  xmm1, xmmword ptr cs:off_140099A20
0x140081529  movaps  [rsp+118h+var_C8], xmm1
0x14008152e  movaps  xmm0, xmmword ptr cs:off_140099A30
0x140081535  movaps  [rsp+118h+var_B8], xmm0
0x14008153a  movaps  xmm1, xmmword ptr cs:off_140099A40
0x140081541  movaps  [rsp+118h+var_A8], xmm1
0x140081546  movaps  xmm0, xmmword ptr cs:off_140099A50
0x14008154d  movaps  [rsp+118h+var_98], xmm0
0x140081555  movaps  xmm1, xmmword ptr cs:off_140099A60
0x14008155c  movaps  [rsp+118h+var_88], xmm1
0x140081564  movaps  xmm0, xmmword ptr cs:off_140099A70
0x14008156b  movaps  xmmword ptr [r11-78h], xmm0
0x140081570  xorps   xmm1, xmm1
0x140081573  xor     eax, eax
0x140081575  movups  [rsp+118h+var_F8], xmm1
0x14008157a  mov     [rsp+118h+var_E8], rax
0x14008157f  xorps   xmm0, xmm0
0x140081582  movups  xmmword ptr [r11-68h], xmm0
0x140081587  movups  xmmword ptr [r11-58h], xmm0
0x14008158c  movups  xmmword ptr [r11-48h], xmm0
0x140081591  test    rcx, rcx
0x140081594  jz      loc_14008165A
0x14008159a  test    edx, edx
0x14008159c  jz      loc_14008165A
0x1400815a2  test    r9, r9
0x1400815a5  jz      loc_14008165A
0x1400815ab  test    r15, r15
0x1400815ae  jz      loc_14008165A
0x1400815b4  test    r14, r14
0x1400815b7  jz      loc_14008165A
0x1400815bd  test    rdi, rdi
0x1400815c0  jz      loc_14008165A
0x1400815c6  mov     [rdi], r13b
0x1400815c9  lea     rax, [r11-68h]
0x1400815cd  mov     qword ptr [rsp+118h+var_D8], rax
0x1400815d2  mov     [r11-68h], rcx
0x1400815d6  mov     [r11-60h], edx
0x1400815da  lea     r9, [rsp+118h+var_F8]
0x1400815df  mov     r8, rcx
0x1400815e2  lea     rdx, [rsp+118h+var_D8]
0x1400815e7  lea     ecx, [r13+2]
0x1400815eb  call    fa_VerifyFontLicensing
0x1400815f0  mov     ecx, eax
0x1400815f2  add     eax, 0Eh
0x1400815f5  test    eax, 0FFFFFFFAh
0x1400815fa  jnz     short loc_140081601
0x1400815fc  cmp     ecx, 0FFFFFFF3h
0x1400815ff  jnz     short loc_140081655
0x140081601  test    ecx, ecx
0x140081603  jnz     short loc_14008165A
0x140081605  cmp     word ptr [rsp+118h+var_F8+8], r13w
0x14008160b  setnz   al
0x14008160e  mov     [rsi], al
0x140081610  movzx   eax, word ptr [rsp+118h+var_F8+6]
0x140081615  mov     [r15], ax
0x140081619  movzx   eax, byte ptr [rsp+118h+var_E8+6]
0x14008161e  mov     [r12], ax
0x140081623  cmp     byte ptr [rsp+118h+var_E8+7], r13b
0x140081628  setz    al
0x14008162b  mov     [r14], al
0x14008162e  cmp     byte ptr [rsp+118h+var_E8+5], r13b
0x140081633  jz      short loc_140081652
0x140081635  xor     r9d, r9d
0x140081638  mov     r8, qword ptr [rsp+118h+var_68]
0x140081640  lea     rdx, [rsp+118h+var_D8]
0x140081645  lea     ecx, [r9+1]
0x140081649  call    fa_VerifyFontLicensing
0x14008164e  test    eax, eax
0x140081650  jnz     short loc_14008165A
0x140081652  mov     byte ptr [rdi], 1
0x140081655  mov     ebx, 1
0x14008165a  mov     r8d, [rsp+118h+var_48]
0x140081662  mov     rdx, [rsp+118h+var_40]
0x14008166a  lea     rcx, [rsp+118h+var_50]
0x140081672  call    EnhancedUnmapRW
0x140081677  mov     eax, ebx
0x140081679  mov     rcx, [rsp+118h+var_38]
0x140081681  xor     rcx, rsp; StackCookie
0x140081684  call    __security_check_cookie
0x140081689  lea     r11, [rsp+118h+var_28]
0x140081691  mov     rbx, [r11+30h]
0x140081695  mov     rsi, [r11+38h]
0x140081699  mov     rsp, r11
0x14008169c  pop     r15
0x14008169e  pop     r14
0x1400816a0  pop     r13
0x1400816a2  pop     r12
0x1400816a4  pop     rdi
0x1400816a5  retn
0x140097ad9  push    rbp
0x140097adb  sub     rsp, 20h
0x140097adf  mov     rbp, rdx
0x140097ae2  mov     r8d, [rbp+0D0h]
0x140097ae9  mov     rdx, [rbp+0D8h]
0x140097af0  lea     rcx, [rbp+0C8h]
0x140097af7  call    EnhancedUnmapRW
0x140097afc  nop
0x140097afd  add     rsp, 20h
0x140097b01  pop     rbp
0x140097b02  retn
```
