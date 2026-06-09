# LuafvLogUtcEvent

- ea: `0x140023d14`
- end: `0x140024052`
- name: `LuafvLogUtcEvent`
- size: `830`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1400157d4`
- `0x140017648`
- `0x140022de8`

## callees

- `0x140001008`
- `0x140001040`
- `0x140005f30`
- `0x140014a1c`
- `0x140018ce8`
- `0x14001dd90`
- `0x140023d14`

## import_xrefs

- `ntoskrnl!SeLocateProcessImageName` at `0x140023d99`
- `ntoskrnl!SeLocateProcessImageName` at `0x140023d99`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023e3a`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023e9b`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023e3a`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023e9b`
- `FLTMGR!FltGetRequestorProcess` at `0x140023d76`
- `FLTMGR!FltGetRequestorProcess` at `0x140023d76`

## pseudocode

```c
__int64 __fastcall LuafvLogUtcEvent(int *a1, __int64 a2, __int64 a3, struct _FLT_CALLBACK_DATA *a4, __int64 a5, int a6)
{
  __int64 v6; // rbx
  int *v7; // r12
  __int64 v8; // rdi
  struct _KPROCESS *RequestorProcess; // rax
  __int64 v11; // r15
  int v12; // ebx
  __int64 v13; // r14
  unsigned __int16 *v14; // rdi
  __int64 v15; // rax
  unsigned __int64 v16; // rax
  __int64 v17; // rsi
  __int64 v18; // rbx
  int v19; // r12d
  __int64 v20; // rax
  __int128 v21; // rt0
  int v22; // eax
  unsigned __int16 *v23; // rsi
  unsigned int v24; // eax
  int v25; // ecx
  __int64 v26; // rax
  __int128 v27; // xmm0
  char v28; // bl
  char v29; // al
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  char *v33; // rdx
  int v34; // [rsp+20h] [rbp-E0h]
  NTSTATUS v35; // [rsp+30h] [rbp-D0h]
  __int128 v36; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v37; // [rsp+48h] [rbp-B8h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v39; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v40; // [rsp+70h] [rbp-90h] BYREF
  int *v41; // [rsp+80h] [rbp-80h]
  __int64 v42; // [rsp+88h] [rbp-78h]
  __int64 v43; // [rsp+90h] [rbp-70h]
  __int128 v44; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h]
  __int64 v48; // [rsp+E0h] [rbp-20h]
  _DWORD v49[2]; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD *v50; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]
  __int64 v52; // [rsp+100h] [rbp+0h]
  _DWORD v53[2]; // [rsp+108h] [rbp+8h] BYREF

  v6 = a5;
  v7 = a1;
  v41 = a1;
  v43 = a5;
  *(_QWORD *)&v44 = a4;
  pImageFileName = 0;
  v37 = 0;
  v8 = (__int64)a4;
  v42 = a2;
  v39 = 0;
  v36 = 0;
  RequestorProcess = FltGetRequestorProcess(a4);
  if ( !RequestorProcess )
    return 3221227292LL;
  v35 = SeLocateProcessImageName(RequestorProcess, &pImageFileName);
  if ( v35 >= 0 )
  {
    v40 = *pImageFileName;
    LuafvExtractFileNameFromPath((__int64)&v37, &v40.Length);
    v11 = *((_QWORD *)&v37 + 1);
    if ( *((_QWORD *)&v37 + 1) )
    {
      v12 = 0;
      v13 = (unsigned __int16)v37 >> 1;
      v14 = (unsigned __int16 *)*((_QWORD *)&v37 + 1);
      v15 = (unsigned __int16)v37 >> 3;
      if ( (_DWORD)v15 )
      {
        v16 = *((_QWORD *)&v37 + 1) + 8 * v15;
        v17 = 0;
        *(_QWORD *)&v40.Length = v16;
        do
        {
          v18 = *(_QWORD *)v14;
          if ( (*(_QWORD *)v14 & 0xFF80FF80FF80FF80uLL) != 0 )
          {
            v19 = 4;
            do
            {
              v20 = (unsigned __int16)v18;
              if ( (unsigned __int16)v18 >= 0x61u )
              {
                if ( (unsigned __int16)v18 <= 0x7Au )
                  v20 = (unsigned int)(unsigned __int16)v18 - 32;
                else
                  v20 = RtlUpcaseUnicodeChar(v18);
              }
              *(_QWORD *)&v21 = v18;
              *((_QWORD *)&v21 + 1) = v20;
              v18 = v21 >> 16;
              --v19;
            }
            while ( v19 );
            v16 = *(_QWORD *)&v40.Length;
          }
          else
          {
            v18 &= 0xFFDFFFDFFFDFFFDFuLL;
          }
          v14 += 4;
          v17 = v18 ^ __ROL8__(v17, 1);
        }
        while ( (unsigned __int64)v14 < v16 );
        v7 = v41;
        v13 &= 3u;
        v22 = v17 ^ __ROR8__(v17, 33);
        v12 = v22 ^ __ROR4__(v22, 17);
      }
      v23 = &v14[v13];
      while ( v14 < v23 )
      {
        v24 = *v14;
        if ( v24 >= 0x61 )
        {
          if ( v24 <= 0x7A )
            v24 -= 32;
          else
            v24 = RtlUpcaseUnicodeChar(v24);
        }
        v12 = v24 ^ __ROL4__(v12, 1);
        ++v14;
      }
      v25 = v12 ^ __ROR4__(v12, 8);
      v26 = 0;
      while ( *(_DWORD *)(v42 + 4 * v26) != v25 )
      {
        if ( (unsigned __int64)++v26 >= 0x10 )
        {
          v6 = v43;
          v8 = v44;
          *(_DWORD *)(v42 + 4LL * (unsigned int)*v7) = v25;
          *v7 = ((unsigned __int8)*v7 + 1) & 0xF;
          goto LABEL_29;
        }
      }
      return (unsigned int)v35;
    }
LABEL_29:
    if ( v6 )
    {
      v27 = *(_OWORD *)(v6 + 16);
      v28 = 0;
      v39 = v27;
    }
    else
    {
      v39 = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 16) + 8LL) + 88LL);
      v29 = LuafvSupplyFullPath(v8, (__int64)&v39);
      v27 = v39;
      v28 = v29;
    }
    v44 = v27;
    LuafvExtractFileNameFromPath((__int64)&v36, (unsigned __int16 *)&v44);
    if ( a6 == 1 )
    {
      if ( (unsigned int)dword_14000E010 <= 5 || !(unsigned __int8)tlgKeywordOn((unsigned int)(a6 - 1)) )
        goto LABEL_45;
      v33 = (char *)&word_14000B3CA;
    }
    else
    {
      v30 = (unsigned int)(a6 - 2);
      if ( a6 == 2 )
      {
        if ( (unsigned int)dword_14000E010 <= 5 || !(unsigned __int8)tlgKeywordOn(v30) )
          goto LABEL_45;
        v33 = byte_14000B311;
      }
      else
      {
        if ( a6 != 3 || (unsigned int)dword_14000E010 <= 5 || !(unsigned __int8)tlgKeywordOn(v30) )
          goto LABEL_45;
        v33 = byte_14000B36B;
      }
    }
    v47 = 2;
    v46 = v49;
    v48 = v11;
    v49[0] = v37 & 0xFFFE;
    v50 = v53;
    v52 = *((_QWORD *)&v36 + 1);
    v49[1] = 0;
    v53[0] = v36 & 0xFFFE;
    v51 = 2;
    v53[1] = 0;
    tlgWriteTransfer_EtwWriteTransfer(4294967294LL, (unsigned __int8 *)v33, v31, v32, v34, &v45);
LABEL_45:
    if ( v28 )
      LuafvFreePool(*((__int64 *)&v39 + 1));
  }
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x140023d14  push    rbp
0x140023d16  push    rbx
0x140023d17  push    rsi
0x140023d18  push    rdi
0x140023d19  push    r12
0x140023d1b  push    r14
0x140023d1d  push    r15
0x140023d1f  lea     rbp, [rsp-20h]
0x140023d24  sub     rsp, 120h
0x140023d2b  mov     rax, cs:__security_cookie
0x140023d32  xor     rax, rsp
0x140023d35  mov     [rbp+50h+var_40], rax
0x140023d39  mov     rbx, [rbp+50h+arg_20]
0x140023d40  xorps   xmm0, xmm0
0x140023d43  mov     r12, rcx
0x140023d46  mov     [rbp+50h+var_D0], rcx
0x140023d4a  xorps   xmm1, xmm1
0x140023d4d  mov     [rbp+50h+var_C0], rbx
0x140023d51  xor     r14d, r14d
0x140023d54  mov     qword ptr [rbp+50h+var_B0], r9
0x140023d58  mov     rcx, r9; CallbackData
0x140023d5b  mov     [rsp+150h+pImageFileName], r14
0x140023d60  movups  [rsp+150h+var_108], xmm0
0x140023d65  mov     rdi, r9
0x140023d68  mov     [rbp+50h+var_C8], rdx
0x140023d6c  movups  [rsp+150h+var_F0], xmm1
0x140023d71  movups  [rsp+150h+var_118], xmm0
0x140023d76  call    cs:__imp_FltGetRequestorProcess
0x140023d7d  nop     dword ptr [rax+rax+00h]
0x140023d82  test    rax, rax
0x140023d85  jnz     short loc_140023D91
0x140023d87  mov     eax, 0C000071Ch
0x140023d8c  jmp     loc_140024033
0x140023d91  lea     rdx, [rsp+150h+pImageFileName]; pImageFileName
0x140023d96  mov     rcx, rax; Process
0x140023d99  call    cs:__imp_SeLocateProcessImageName
0x140023da0  nop     dword ptr [rax+rax+00h]
0x140023da5  mov     [rsp+150h+var_120], eax
0x140023da9  test    eax, eax
0x140023dab  js      loc_14002402F
0x140023db1  mov     rcx, [rsp+150h+pImageFileName]
0x140023db6  lea     rdx, [rsp+150h+var_E0]
0x140023dbb  movups  xmm0, xmmword ptr [rcx]
0x140023dbe  lea     rcx, [rsp+150h+var_108]
0x140023dc3  movdqu  [rsp+150h+var_E0], xmm0
0x140023dc9  call    LuafvExtractFileNameFromPath
0x140023dce  mov     r15, qword ptr [rsp+150h+var_108+8]
0x140023dd3  test    r15, r15
0x140023dd6  jz      loc_140023EFB
0x140023ddc  movzx   r14d, word ptr [rsp+150h+var_108]
0x140023de2  xor     ebx, ebx
0x140023de4  shr     r14d, 1
0x140023de7  mov     rdi, r15
0x140023dea  mov     eax, r14d
0x140023ded  shr     eax, 2
0x140023df0  test    eax, eax
0x140023df2  jz      loc_140023E85
0x140023df8  lea     rax, [r15+rax*8]
0x140023dfc  xor     esi, esi
0x140023dfe  mov     qword ptr [rsp+150h+var_E0], rax
0x140023e03  mov     rbx, [rdi]
0x140023e06  mov     rcx, 0FF80FF80FF80FF80h
0x140023e10  test    rcx, rbx
0x140023e13  jnz     short loc_140023E24
0x140023e15  mov     rcx, 0FFDFFFDFFFDFFFDFh
0x140023e1f  and     rbx, rcx
0x140023e22  jmp     short loc_140023E5E
0x140023e24  mov     r12d, 4
0x140023e2a  movzx   eax, bx
0x140023e2d  cmp     eax, 61h ; 'a'
0x140023e30  jb      short loc_140023E4E
0x140023e32  cmp     eax, 7Ah ; 'z'
0x140023e35  jbe     short loc_140023E4B
0x140023e37  movzx   ecx, ax; SourceCharacter
0x140023e3a  call    cs:__imp_RtlUpcaseUnicodeChar
0x140023e41  nop     dword ptr [rax+rax+00h]
0x140023e46  movzx   eax, ax
0x140023e49  jmp     short loc_140023E4E
0x140023e4b  add     eax, 0FFFFFFE0h
0x140023e4e  shrd    rbx, rax, 10h
0x140023e53  add     r12d, 0FFFFFFFFh
0x140023e57  jnz     short loc_140023E2A
0x140023e59  mov     rax, qword ptr [rsp+150h+var_E0]
0x140023e5e  rol     rsi, 1
0x140023e61  add     rdi, 8
0x140023e65  xor     rsi, rbx
0x140023e68  cmp     rdi, rax
0x140023e6b  jb      short loc_140023E03
0x140023e6d  mov     r12, [rbp+50h+var_D0]
0x140023e71  mov     rax, rsi
0x140023e74  ror     rax, 21h
0x140023e78  and     r14d, 3
0x140023e7c  xor     eax, esi
0x140023e7e  mov     ebx, eax
0x140023e80  ror     ebx, 11h
0x140023e83  xor     ebx, eax
0x140023e85  lea     rsi, [rdi+r14*2]
0x140023e89  jmp     short loc_140023EB7
0x140023e8b  movzx   eax, word ptr [rdi]
0x140023e8e  cmp     eax, 61h ; 'a'
0x140023e91  jb      short loc_140023EAF
0x140023e93  cmp     eax, 7Ah ; 'z'
0x140023e96  jbe     short loc_140023EAC
0x140023e98  movzx   ecx, ax; SourceCharacter
0x140023e9b  call    cs:__imp_RtlUpcaseUnicodeChar
0x140023ea2  nop     dword ptr [rax+rax+00h]
0x140023ea7  movzx   eax, ax
0x140023eaa  jmp     short loc_140023EAF
0x140023eac  add     eax, 0FFFFFFE0h
0x140023eaf  rol     ebx, 1
0x140023eb1  xor     ebx, eax
0x140023eb3  add     rdi, 2
0x140023eb7  cmp     rdi, rsi
0x140023eba  jb      short loc_140023E8B
0x140023ebc  mov     rdx, [rbp+50h+var_C8]
0x140023ec0  mov     ecx, ebx
0x140023ec2  ror     ecx, 8
0x140023ec5  xor     ecx, ebx
0x140023ec7  xor     r14d, r14d
0x140023eca  mov     eax, r14d
0x140023ecd  cmp     [rdx+rax*4], ecx
0x140023ed0  jz      loc_14002402F
0x140023ed6  inc     rax
0x140023ed9  cmp     rax, 10h
0x140023edd  jb      short loc_140023ECD
0x140023edf  mov     eax, [r12]
0x140023ee3  mov     rbx, [rbp+50h+var_C0]
0x140023ee7  mov     rdi, qword ptr [rbp+50h+var_B0]
0x140023eeb  mov     [rdx+rax*4], ecx
0x140023eee  mov     eax, [r12]
0x140023ef2  inc     eax
0x140023ef4  and     eax, 0Fh
0x140023ef7  mov     [r12], eax
0x140023efb  test    rbx, rbx
0x140023efe  jz      short loc_140023F0E
0x140023f00  movups  xmm0, xmmword ptr [rbx+10h]
0x140023f04  mov     bl, r14b
0x140023f07  movaps  [rsp+150h+var_F0], xmm0
0x140023f0c  jmp     short loc_140023F34
0x140023f0e  mov     rax, [rdi+10h]
0x140023f12  mov     rcx, rdi
0x140023f15  mov     rdx, [rax+8]
0x140023f19  movups  xmm0, xmmword ptr [rdx+58h]
0x140023f1d  lea     rdx, [rsp+150h+var_F0]
0x140023f22  movdqu  [rsp+150h+var_F0], xmm0
0x140023f28  call    LuafvSupplyFullPath
0x140023f2d  movaps  xmm0, [rsp+150h+var_F0]
0x140023f32  mov     bl, al
0x140023f34  lea     rdx, [rbp+50h+var_B0]
0x140023f38  movdqa  [rbp+50h+var_B0], xmm0
0x140023f3d  lea     rcx, [rsp+150h+var_118]
0x140023f42  call    LuafvExtractFileNameFromPath
0x140023f47  mov     ecx, [rbp+50h+arg_28]
0x140023f4d  sub     ecx, 1
0x140023f50  jz      short loc_140023FAA
0x140023f52  sub     ecx, 1
0x140023f55  jz      short loc_140023F85
0x140023f57  cmp     ecx, 1
0x140023f5a  jnz     loc_140024021
0x140023f60  mov     eax, cs:dword_14000E010
0x140023f66  cmp     eax, 5
0x140023f69  jbe     loc_140024021
0x140023f6f  call    _tlgKeywordOn
0x140023f74  test    al, al
0x140023f76  jz      loc_140024021
0x140023f7c  lea     rdx, byte_14000B36B
0x140023f83  jmp     short loc_140023FC5
0x140023f85  mov     eax, cs:dword_14000E010
0x140023f8b  cmp     eax, 5
0x140023f8e  jbe     loc_140024021
0x140023f94  call    _tlgKeywordOn
0x140023f99  test    al, al
0x140023f9b  jz      loc_140024021
0x140023fa1  lea     rdx, byte_14000B311
0x140023fa8  jmp     short loc_140023FC5
0x140023faa  mov     eax, cs:dword_14000E010
0x140023fb0  cmp     eax, 5
0x140023fb3  jbe     short loc_140024021
0x140023fb5  call    _tlgKeywordOn
0x140023fba  test    al, al
0x140023fbc  jz      short loc_140024021
0x140023fbe  lea     rdx, word_14000B3CA; int
0x140023fc5  lea     rax, [rbp+50h+var_68]
0x140023fc9  mov     [rbp+50h+var_78], 2
0x140023fd1  mov     [rbp+50h+var_80], rax
0x140023fd5  mov     ecx, 0FFFFFFFEh; int
0x140023fda  movzx   eax, word ptr [rsp+150h+var_108]
0x140023fdf  and     eax, ecx
0x140023fe1  mov     [rbp+50h+var_70], r15
0x140023fe5  mov     [rbp+50h+var_68], eax
0x140023fe8  lea     rax, [rbp+50h+var_48]
0x140023fec  mov     [rbp+50h+var_60], rax
0x140023ff0  mov     rax, qword ptr [rsp+150h+var_118+8]
0x140023ff5  mov     [rbp+50h+var_50], rax
0x140023ff9  movzx   eax, word ptr [rsp+150h+var_118]
0x140023ffe  and     eax, ecx
0x140024000  mov     [rbp+50h+var_64], r14d
0x140024004  mov     [rbp+50h+var_48], eax
0x140024007  lea     rax, [rbp+50h+var_A0]
0x14002400b  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x140024010  mov     [rbp+50h+var_58], 2
0x140024018  mov     [rbp+50h+var_44], r14d
0x14002401c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140024021  test    bl, bl
0x140024023  jz      short loc_14002402F
0x140024025  mov     rcx, qword ptr [rsp+150h+var_F0+8]
0x14002402a  call    LuafvFreePool
0x14002402f  mov     eax, [rsp+150h+var_120]
0x140024033  mov     rcx, [rbp+50h+var_40]
0x140024037  xor     rcx, rsp; StackCookie
0x14002403a  call    __security_check_cookie
0x14002403f  add     rsp, 120h
0x140024046  pop     r15
0x140024048  pop     r14
0x14002404a  pop     r12
0x14002404c  pop     rdi
0x14002404d  pop     rsi
0x14002404e  pop     rbx
0x14002404f  pop     rbp
0x140024050  retn
```
