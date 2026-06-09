# CDockInterface::DeviceInstancePathToVisibleDock(unsigned __int64,ushort const *,_VISIBLE_DOCK *)

- ea: `0x18001ad60`
- end: `0x18001afbd`
- name: `?DeviceInstancePathToVisibleDock@CDockInterface@@AEAAJ_KPEBGPEAU_VISIBLE_DOCK@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(DockingProviders **this, unsigned __int64, const unsigned __int16 *, struct _VISIBLE_DOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001abac`

## callees

- `0x180001dc8`
- `0x18000c308`
- `0x180016374`
- `0x18001ad60`
- `0x18001ca70`

## import_xrefs

- `msvcrt!wcstoul` at `0x18001ae7b`
- `msvcrt!wcstoul` at `0x18001ae7b`

## pseudocode

```c
__int64 __fastcall CDockInterface::DeviceInstancePathToVisibleDock(
        DockingProviders **this,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        struct _VISIBLE_DOCK *a4)
{
  const unsigned __int16 *v5; // r12
  unsigned __int64 v6; // r15
  __int64 v8; // rdi
  int v9; // r9d
  __int64 v10; // rsi
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned int v13; // r14d
  __int64 v14; // rdx
  wchar_t v15; // cx
  char v16; // al
  __int64 v17; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-278h]
  wchar_t *EndPtr; // [rsp+28h] [rbp-270h] BYREF
  wchar_t String[8]; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int16 v24[264]; // [rsp+40h] [rbp-258h] BYREF

  v5 = a3;
  v6 = a2;
  if ( !a3 || !a4 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 25)
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return 2147942487LL;
    }
    v20 = 34;
    goto LABEL_38;
  }
  v8 = 0;
  LOWORD(v9) = 0;
  LOBYTE(a2) = 0;
  v21 = 0;
  LOBYTE(a3) = 0;
  v10 = 0;
  if ( !v6 )
  {
LABEL_30:
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 25)
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return 2147942487LL;
    }
    v20 = 36;
LABEL_38:
    WPP_SF_q(v19[2], v20, &WPP_b415491bb2933ebae3e7436051291308_Traceguids, this);
    return 2147942487LL;
  }
  do
  {
    if ( (unsigned int)v8 >= 0x104 )
      goto LABEL_25;
    v11 = v5[v10];
    if ( (_WORD)v11 == 123 )
    {
      LOBYTE(a3) = 1;
      LOBYTE(a2) = 0;
    }
    else if ( (_WORD)v11 == 40 )
    {
      LOBYTE(a2) = 1;
      LOBYTE(a3) = 0;
    }
    else if ( (_BYTE)a2 )
    {
      v12 = (unsigned int)v8;
      if ( (_WORD)v11 == 41 )
      {
        if ( v12 >= 260 )
          goto LABEL_40;
        LOBYTE(a2) = 0;
        LOWORD(v11) = 0;
      }
      else
      {
        v8 = (unsigned int)(v8 + 1);
      }
      v24[v12] = v11;
    }
    else if ( (_BYTE)a3 )
    {
      v13 = 0;
      if ( (unsigned int)(v10 + 1) >= v6 )
        goto LABEL_30;
      while ( v13 < 0xC )
      {
        v14 = v13 + (unsigned int)v10;
        v15 = v5[v14];
        String[1] = v5[(unsigned int)(v14 + 1)];
        String[0] = v15;
        String[2] = 0;
        EndPtr = 0;
        v16 = wcstoul(String, &EndPtr, 16);
        HIWORD(v9) = HIWORD(v21);
        v13 += 2;
        v17 = (unsigned __int16)v21;
        LOWORD(v9) = v21 + 1;
        v21 = v9;
        *((_BYTE *)a4 + v17 + 528) = v16;
        if ( (unsigned int)v10 + v13 + 1 >= v6 )
          goto LABEL_21;
      }
      goto LABEL_22;
    }
    v10 = (unsigned int)(v10 + 1);
  }
  while ( (unsigned int)v10 < v6 );
LABEL_21:
  if ( (unsigned int)v8 >= 0x104 )
  {
LABEL_25:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_b415491bb2933ebae3e7436051291308_Traceguids, this);
    }
    return 2147942511LL;
  }
LABEL_22:
  if ( (_WORD)v9 != 6 )
    goto LABEL_30;
  v11 = 2 * v8;
  if ( (unsigned __int64)(2 * v8) >= 0x208 )
LABEL_40:
    _report_rangecheckfailure(v11, a2, a3);
  v24[v8] = 0;
  *((_QWORD *)a4 + 143) = DockingProviders::ProviderIndex(this[2], v24);
  return 0;
}

```

## disassembly

```asm
0x18001ad60  mov     [rsp+arg_8], rbx
0x18001ad65  push    rbp
0x18001ad66  push    rsi
0x18001ad67  push    rdi
0x18001ad68  push    r12
0x18001ad6a  push    r13
0x18001ad6c  push    r14
0x18001ad6e  push    r15
0x18001ad70  sub     rsp, 260h
0x18001ad77  mov     rax, cs:__security_cookie
0x18001ad7e  xor     rax, rsp
0x18001ad81  mov     [rsp+298h+var_48], rax
0x18001ad89  mov     r13, r9
0x18001ad8c  mov     r12, r8
0x18001ad8f  mov     r15, rdx
0x18001ad92  mov     rbp, rcx
0x18001ad95  test    r8, r8
0x18001ad98  jz      loc_18001AF4F
0x18001ad9e  test    r9, r9
0x18001ada1  jz      loc_18001AF4F
0x18001ada7  xor     edi, edi
0x18001ada9  xor     r9d, r9d
0x18001adac  xor     dl, dl
0x18001adae  mov     [rsp+298h+var_278], r9d
0x18001adb3  xor     r8b, r8b
0x18001adb6  xor     esi, esi
0x18001adb8  lea     ebx, [rdi+1]
0x18001adbb  test    r15, r15
0x18001adbe  jz      loc_18001AF2B
0x18001adc4  cmp     edi, 104h
0x18001adca  jnb     loc_18001AEEF
0x18001add0  movzx   ecx, word ptr [r12+rsi*2]
0x18001add5  mov     eax, 7Bh ; '{'
0x18001adda  cmp     ax, cx
0x18001addd  jnz     short loc_18001ADE6
0x18001addf  mov     r8b, bl
0x18001ade2  xor     dl, dl
0x18001ade4  jmp     short loc_18001AE26
0x18001ade6  mov     eax, 28h ; '('
0x18001adeb  cmp     ax, cx
0x18001adee  jnz     short loc_18001ADF7
0x18001adf0  mov     dl, bl
0x18001adf2  xor     r8b, r8b
0x18001adf5  jmp     short loc_18001AE26
0x18001adf7  test    dl, dl
0x18001adf9  jz      short loc_18001AE21
0x18001adfb  mov     eax, edi
0x18001adfd  add     rax, rax
0x18001ae00  cmp     cx, 29h ; ')'
0x18001ae04  jnz     short loc_18001AE18
0x18001ae06  cmp     rax, 208h
0x18001ae0c  jnb     loc_18001AFB7
0x18001ae12  xor     dl, dl
0x18001ae14  xor     ecx, ecx
0x18001ae16  jmp     short loc_18001AE1A
0x18001ae18  add     edi, ebx
0x18001ae1a  mov     [rsp+rax+298h+var_258], cx
0x18001ae1f  jmp     short loc_18001AE26
0x18001ae21  test    r8b, r8b
0x18001ae24  jnz     short loc_18001AE31
0x18001ae26  add     esi, ebx
0x18001ae28  mov     eax, esi
0x18001ae2a  cmp     rax, r15
0x18001ae2d  jb      short loc_18001ADC4
0x18001ae2f  jmp     short loc_18001AEAA
0x18001ae31  xor     r14d, r14d
0x18001ae34  lea     ecx, [rsi+1]
0x18001ae37  cmp     rcx, r15
0x18001ae3a  jnb     loc_18001AF2B
0x18001ae40  cmp     r14d, 0Ch
0x18001ae44  jnb     short loc_18001AEB2
0x18001ae46  lea     edx, [r14+rsi]
0x18001ae4a  movzx   ecx, word ptr [r12+rdx*2]
0x18001ae4f  lea     eax, [rdx+1]
0x18001ae52  movzx   eax, word ptr [r12+rax*2]
0x18001ae57  lea     rdx, [rsp+298h+EndPtr]; EndPtr
0x18001ae5c  mov     [rsp+298h+var_266], ax
0x18001ae61  xor     eax, eax
0x18001ae63  mov     [rsp+298h+String], cx
0x18001ae68  lea     rcx, [rsp+298h+String]; String
0x18001ae6d  mov     [rsp+298h+var_264], ax
0x18001ae72  mov     [rsp+298h+EndPtr], rax
0x18001ae77  lea     r8d, [rax+10h]; Radix
0x18001ae7b  call    cs:__imp_wcstoul
0x18001ae81  mov     r9d, [rsp+298h+var_278]
0x18001ae86  add     r14d, 2
0x18001ae8a  movzx   ecx, r9w
0x18001ae8e  add     r9w, bx
0x18001ae92  mov     [rsp+298h+var_278], r9d
0x18001ae97  mov     [rcx+r13+210h], al
0x18001ae9f  lea     ecx, [r14+1]
0x18001aea3  add     ecx, esi
0x18001aea5  cmp     rcx, r15
0x18001aea8  jb      short loc_18001AE40
0x18001aeaa  cmp     edi, 104h
0x18001aeb0  jnb     short loc_18001AEEF
0x18001aeb2  cmp     r9w, 6
0x18001aeb7  jnz     short loc_18001AF2B
0x18001aeb9  lea     rcx, [rdi+rdi]
0x18001aebd  cmp     rcx, 208h
0x18001aec4  jnb     loc_18001AFB7
0x18001aeca  xor     eax, eax
0x18001aecc  lea     rdx, [rsp+298h+var_258]; unsigned __int16 *
0x18001aed1  mov     [rsp+rcx+298h+var_258], ax
0x18001aed6  mov     rcx, [rbp+10h]; this
0x18001aeda  call    ?ProviderIndex@DockingProviders@@QEAAIPEBG@Z; DockingProviders::ProviderIndex(ushort const *)
0x18001aedf  mov     eax, eax
0x18001aee1  mov     [r13+478h], rax
0x18001aee8  xor     eax, eax
0x18001aeea  jmp     loc_18001AF8C
0x18001aeef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aef6  lea     rax, WPP_GLOBAL_Control
0x18001aefd  cmp     rcx, rax
0x18001af00  jz      short loc_18001AF24
0x18001af02  cmp     [rcx+19h], bl
0x18001af05  jb      short loc_18001AF24
0x18001af07  test    [rcx+1Ch], bl
0x18001af0a  jz      short loc_18001AF24
0x18001af0c  mov     rcx, [rcx+10h]
0x18001af10  lea     r8, WPP_b415491bb2933ebae3e7436051291308_Traceguids
0x18001af17  mov     edx, 23h ; '#'
0x18001af1c  mov     r9, rbp
0x18001af1f  call    WPP_SF_q
0x18001af24  mov     eax, 8007006Fh
0x18001af29  jmp     short loc_18001AF8C
0x18001af2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af32  lea     rax, WPP_GLOBAL_Control
0x18001af39  cmp     rcx, rax
0x18001af3c  jz      short loc_18001AF87
0x18001af3e  cmp     [rcx+19h], bl
0x18001af41  jb      short loc_18001AF87
0x18001af43  test    [rcx+1Ch], bl
0x18001af46  jz      short loc_18001AF87
0x18001af48  mov     edx, 24h ; '$'
0x18001af4d  jmp     short loc_18001AF74
0x18001af4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af56  lea     rax, WPP_GLOBAL_Control
0x18001af5d  cmp     rcx, rax
0x18001af60  jz      short loc_18001AF87
0x18001af62  mov     ebx, 1
0x18001af67  cmp     [rcx+19h], bl
0x18001af6a  jb      short loc_18001AF87
0x18001af6c  test    [rcx+1Ch], bl
0x18001af6f  jz      short loc_18001AF87
0x18001af71  lea     edx, [rbx+21h]
0x18001af74  mov     rcx, [rcx+10h]
0x18001af78  lea     r8, WPP_b415491bb2933ebae3e7436051291308_Traceguids
0x18001af7f  mov     r9, rbp
0x18001af82  call    WPP_SF_q
0x18001af87  mov     eax, 80070057h
0x18001af8c  mov     rcx, [rsp+298h+var_48]
0x18001af94  xor     rcx, rsp; StackCookie
0x18001af97  call    __security_check_cookie
0x18001af9c  mov     rbx, [rsp+298h+arg_8]
0x18001afa4  add     rsp, 260h
0x18001afab  pop     r15
0x18001afad  pop     r14
0x18001afaf  pop     r13
0x18001afb1  pop     r12
0x18001afb3  pop     rdi
0x18001afb4  pop     rsi
0x18001afb5  pop     rbp
0x18001afb6  retn
0x18001afb7  call    __report_rangecheckfailure
```
