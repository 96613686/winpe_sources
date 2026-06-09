# LuafvLogUtcEvent

- ea: `0x140023cc4`
- end: `0x140024002`
- name: `LuafvLogUtcEvent`
- size: `830`
- prototype: `__int64 __fastcall(int *, __int64, __int64, struct _FLT_CALLBACK_DATA *, UNICODE_STRING *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1400157d4`
- `0x1400175f8`
- `0x140022d98`

## callees

- `0x140001008`
- `0x140001040`
- `0x140005bb0`
- `0x140014a1c`
- `0x140018c98`
- `0x14001dd40`
- `0x140023cc4`

## import_xrefs

- `ntoskrnl!SeLocateProcessImageName` at `0x140023d49`
- `ntoskrnl!SeLocateProcessImageName` at `0x140023d49`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023dea`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023e4b`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023dea`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023e4b`
- `FLTMGR!FltGetRequestorProcess` at `0x140023d26`
- `FLTMGR!FltGetRequestorProcess` at `0x140023d26`

## pseudocode

```c
__int64 __fastcall LuafvLogUtcEvent(
        int *a1,
        __int64 a2,
        __int64 a3,
        struct _FLT_CALLBACK_DATA *a4,
        UNICODE_STRING *a5,
        int a6)
{
  UNICODE_STRING *v6; // rbx
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
  UNICODE_STRING v27; // xmm0
  char v28; // bl
  char v29; // al
  __int64 v30; // r8
  __int64 v31; // r9
  char *v32; // rdx
  int v33; // [rsp+20h] [rbp-E0h]
  NTSTATUS v34; // [rsp+30h] [rbp-D0h]
  __int128 v35; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v36; // [rsp+48h] [rbp-B8h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING v38; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v39; // [rsp+70h] [rbp-90h] BYREF
  int *v40; // [rsp+80h] [rbp-80h]
  __int64 v41; // [rsp+88h] [rbp-78h]
  UNICODE_STRING *v42; // [rsp+90h] [rbp-70h]
  UNICODE_STRING v43; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v44; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  __int64 v47; // [rsp+E0h] [rbp-20h]
  _DWORD v48[2]; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD *v49; // [rsp+F0h] [rbp-10h]
  __int64 v50; // [rsp+F8h] [rbp-8h]
  __int64 v51; // [rsp+100h] [rbp+0h]
  _DWORD v52[2]; // [rsp+108h] [rbp+8h] BYREF

  v6 = a5;
  v7 = a1;
  v40 = a1;
  v42 = a5;
  *(_QWORD *)&v43.Length = a4;
  pImageFileName = 0;
  v36 = 0;
  v8 = (__int64)a4;
  v41 = a2;
  v38 = 0;
  v35 = 0;
  RequestorProcess = FltGetRequestorProcess(a4);
  if ( !RequestorProcess )
    return 3221227292LL;
  v34 = SeLocateProcessImageName(RequestorProcess, &pImageFileName);
  if ( v34 >= 0 )
  {
    v39 = *pImageFileName;
    LuafvExtractFileNameFromPath((__int64)&v36, (__int64)&v39);
    v11 = *((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) )
    {
      v12 = 0;
      v13 = (unsigned __int16)v36 >> 1;
      v14 = (unsigned __int16 *)*((_QWORD *)&v36 + 1);
      v15 = (unsigned __int16)v36 >> 3;
      if ( (_DWORD)v15 )
      {
        v16 = *((_QWORD *)&v36 + 1) + 8 * v15;
        v17 = 0;
        *(_QWORD *)&v39.Length = v16;
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
            v16 = *(_QWORD *)&v39.Length;
          }
          else
          {
            v18 &= 0xFFDFFFDFFFDFFFDFuLL;
          }
          v14 += 4;
          v17 = v18 ^ __ROL8__(v17, 1);
        }
        while ( (unsigned __int64)v14 < v16 );
        v7 = v40;
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
      while ( *(_DWORD *)(v41 + 4 * v26) != v25 )
      {
        if ( (unsigned __int64)++v26 >= 0x10 )
        {
          v6 = v42;
          v8 = *(_QWORD *)&v43.Length;
          *(_DWORD *)(v41 + 4LL * (unsigned int)*v7) = v25;
          *v7 = ((unsigned __int8)*v7 + 1) & 0xF;
          goto LABEL_29;
        }
      }
      return (unsigned int)v34;
    }
LABEL_29:
    if ( v6 )
    {
      v27 = v6[1];
      v28 = 0;
      v38 = v27;
    }
    else
    {
      v38 = *(UNICODE_STRING *)(*(_QWORD *)(*(_QWORD *)(v8 + 16) + 8LL) + 88LL);
      v29 = LuafvSupplyFullPath(v8, &v38);
      v27 = v38;
      v28 = v29;
    }
    v43 = v27;
    LuafvExtractFileNameFromPath((__int64)&v35, (__int64)&v43);
    if ( a6 == 1 )
    {
      if ( (unsigned int)dword_14000E010 <= 5 || !tlgKeywordOn() )
        goto LABEL_45;
      v32 = (char *)&word_14000B3CA;
    }
    else if ( a6 == 2 )
    {
      if ( (unsigned int)dword_14000E010 <= 5 || !tlgKeywordOn() )
        goto LABEL_45;
      v32 = byte_14000B311;
    }
    else
    {
      if ( a6 != 3 || (unsigned int)dword_14000E010 <= 5 || !tlgKeywordOn() )
        goto LABEL_45;
      v32 = byte_14000B36B;
    }
    v46 = 2;
    v45 = v48;
    v47 = v11;
    v48[0] = v36 & 0xFFFE;
    v49 = v52;
    v51 = *((_QWORD *)&v35 + 1);
    v48[1] = 0;
    v52[0] = v35 & 0xFFFE;
    v50 = 2;
    v52[1] = 0;
    tlgWriteTransfer_EtwWriteTransfer(4294967294LL, (unsigned __int8 *)v32, v30, v31, v33, &v44);
LABEL_45:
    if ( v28 )
      LuafvFreePool((__int64)v38.Buffer);
  }
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x140023cc4  push    rbp
0x140023cc6  push    rbx
0x140023cc7  push    rsi
0x140023cc8  push    rdi
0x140023cc9  push    r12
0x140023ccb  push    r14
0x140023ccd  push    r15
0x140023ccf  lea     rbp, [rsp-20h]
0x140023cd4  sub     rsp, 120h
0x140023cdb  mov     rax, cs:__security_cookie
0x140023ce2  xor     rax, rsp
0x140023ce5  mov     [rbp+50h+var_40], rax
0x140023ce9  mov     rbx, [rbp+50h+arg_20]
0x140023cf0  xorps   xmm0, xmm0
0x140023cf3  mov     r12, rcx
0x140023cf6  mov     [rbp+50h+var_D0], rcx
0x140023cfa  xorps   xmm1, xmm1
0x140023cfd  mov     [rbp+50h+var_C0], rbx
0x140023d01  xor     r14d, r14d
0x140023d04  mov     qword ptr [rbp+50h+var_B0], r9
0x140023d08  mov     rcx, r9; CallbackData
0x140023d0b  mov     [rsp+150h+pImageFileName], r14
0x140023d10  movups  [rsp+150h+var_108], xmm0
0x140023d15  mov     rdi, r9
0x140023d18  mov     [rbp+50h+var_C8], rdx
0x140023d1c  movups  [rsp+150h+var_F0], xmm1
0x140023d21  movups  [rsp+150h+var_118], xmm0
0x140023d26  call    cs:__imp_FltGetRequestorProcess
0x140023d2d  nop     dword ptr [rax+rax+00h]
0x140023d32  test    rax, rax
0x140023d35  jnz     short loc_140023D41
0x140023d37  mov     eax, 0C000071Ch
0x140023d3c  jmp     loc_140023FE3
0x140023d41  lea     rdx, [rsp+150h+pImageFileName]; pImageFileName
0x140023d46  mov     rcx, rax; Process
0x140023d49  call    cs:__imp_SeLocateProcessImageName
0x140023d50  nop     dword ptr [rax+rax+00h]
0x140023d55  mov     [rsp+150h+var_120], eax
0x140023d59  test    eax, eax
0x140023d5b  js      loc_140023FDF
0x140023d61  mov     rcx, [rsp+150h+pImageFileName]
0x140023d66  lea     rdx, [rsp+150h+var_E0]
0x140023d6b  movups  xmm0, xmmword ptr [rcx]
0x140023d6e  lea     rcx, [rsp+150h+var_108]
0x140023d73  movdqu  [rsp+150h+var_E0], xmm0
0x140023d79  call    LuafvExtractFileNameFromPath
0x140023d7e  mov     r15, qword ptr [rsp+150h+var_108+8]
0x140023d83  test    r15, r15
0x140023d86  jz      loc_140023EAB
0x140023d8c  movzx   r14d, word ptr [rsp+150h+var_108]
0x140023d92  xor     ebx, ebx
0x140023d94  shr     r14d, 1
0x140023d97  mov     rdi, r15
0x140023d9a  mov     eax, r14d
0x140023d9d  shr     eax, 2
0x140023da0  test    eax, eax
0x140023da2  jz      loc_140023E35
0x140023da8  lea     rax, [r15+rax*8]
0x140023dac  xor     esi, esi
0x140023dae  mov     qword ptr [rsp+150h+var_E0], rax
0x140023db3  mov     rbx, [rdi]
0x140023db6  mov     rcx, 0FF80FF80FF80FF80h
0x140023dc0  test    rcx, rbx
0x140023dc3  jnz     short loc_140023DD4
0x140023dc5  mov     rcx, 0FFDFFFDFFFDFFFDFh
0x140023dcf  and     rbx, rcx
0x140023dd2  jmp     short loc_140023E0E
0x140023dd4  mov     r12d, 4
0x140023dda  movzx   eax, bx
0x140023ddd  cmp     eax, 61h ; 'a'
0x140023de0  jb      short loc_140023DFE
0x140023de2  cmp     eax, 7Ah ; 'z'
0x140023de5  jbe     short loc_140023DFB
0x140023de7  movzx   ecx, ax; SourceCharacter
0x140023dea  call    cs:__imp_RtlUpcaseUnicodeChar
0x140023df1  nop     dword ptr [rax+rax+00h]
0x140023df6  movzx   eax, ax
0x140023df9  jmp     short loc_140023DFE
0x140023dfb  add     eax, 0FFFFFFE0h
0x140023dfe  shrd    rbx, rax, 10h
0x140023e03  add     r12d, 0FFFFFFFFh
0x140023e07  jnz     short loc_140023DDA
0x140023e09  mov     rax, qword ptr [rsp+150h+var_E0]
0x140023e0e  rol     rsi, 1
0x140023e11  add     rdi, 8
0x140023e15  xor     rsi, rbx
0x140023e18  cmp     rdi, rax
0x140023e1b  jb      short loc_140023DB3
0x140023e1d  mov     r12, [rbp+50h+var_D0]
0x140023e21  mov     rax, rsi
0x140023e24  ror     rax, 21h
0x140023e28  and     r14d, 3
0x140023e2c  xor     eax, esi
0x140023e2e  mov     ebx, eax
0x140023e30  ror     ebx, 11h
0x140023e33  xor     ebx, eax
0x140023e35  lea     rsi, [rdi+r14*2]
0x140023e39  jmp     short loc_140023E67
0x140023e3b  movzx   eax, word ptr [rdi]
0x140023e3e  cmp     eax, 61h ; 'a'
0x140023e41  jb      short loc_140023E5F
0x140023e43  cmp     eax, 7Ah ; 'z'
0x140023e46  jbe     short loc_140023E5C
0x140023e48  movzx   ecx, ax; SourceCharacter
0x140023e4b  call    cs:__imp_RtlUpcaseUnicodeChar
0x140023e52  nop     dword ptr [rax+rax+00h]
0x140023e57  movzx   eax, ax
0x140023e5a  jmp     short loc_140023E5F
0x140023e5c  add     eax, 0FFFFFFE0h
0x140023e5f  rol     ebx, 1
0x140023e61  xor     ebx, eax
0x140023e63  add     rdi, 2
0x140023e67  cmp     rdi, rsi
0x140023e6a  jb      short loc_140023E3B
0x140023e6c  mov     rdx, [rbp+50h+var_C8]
0x140023e70  mov     ecx, ebx
0x140023e72  ror     ecx, 8
0x140023e75  xor     ecx, ebx
0x140023e77  xor     r14d, r14d
0x140023e7a  mov     eax, r14d
0x140023e7d  cmp     [rdx+rax*4], ecx
0x140023e80  jz      loc_140023FDF
0x140023e86  inc     rax
0x140023e89  cmp     rax, 10h
0x140023e8d  jb      short loc_140023E7D
0x140023e8f  mov     eax, [r12]
0x140023e93  mov     rbx, [rbp+50h+var_C0]
0x140023e97  mov     rdi, qword ptr [rbp+50h+var_B0]
0x140023e9b  mov     [rdx+rax*4], ecx
0x140023e9e  mov     eax, [r12]
0x140023ea2  inc     eax
0x140023ea4  and     eax, 0Fh
0x140023ea7  mov     [r12], eax
0x140023eab  test    rbx, rbx
0x140023eae  jz      short loc_140023EBE
0x140023eb0  movups  xmm0, xmmword ptr [rbx+10h]
0x140023eb4  mov     bl, r14b
0x140023eb7  movaps  [rsp+150h+var_F0], xmm0
0x140023ebc  jmp     short loc_140023EE4
0x140023ebe  mov     rax, [rdi+10h]
0x140023ec2  mov     rcx, rdi
0x140023ec5  mov     rdx, [rax+8]
0x140023ec9  movups  xmm0, xmmword ptr [rdx+58h]
0x140023ecd  lea     rdx, [rsp+150h+var_F0]
0x140023ed2  movdqu  [rsp+150h+var_F0], xmm0
0x140023ed8  call    LuafvSupplyFullPath
0x140023edd  movaps  xmm0, [rsp+150h+var_F0]
0x140023ee2  mov     bl, al
0x140023ee4  lea     rdx, [rbp+50h+var_B0]
0x140023ee8  movdqa  [rbp+50h+var_B0], xmm0
0x140023eed  lea     rcx, [rsp+150h+var_118]
0x140023ef2  call    LuafvExtractFileNameFromPath
0x140023ef7  mov     ecx, [rbp+50h+arg_28]
0x140023efd  sub     ecx, 1
0x140023f00  jz      short loc_140023F5A
0x140023f02  sub     ecx, 1
0x140023f05  jz      short loc_140023F35
0x140023f07  cmp     ecx, 1
0x140023f0a  jnz     loc_140023FD1
0x140023f10  mov     eax, cs:dword_14000E010
0x140023f16  cmp     eax, 5
0x140023f19  jbe     loc_140023FD1
0x140023f1f  call    _tlgKeywordOn
0x140023f24  test    al, al
0x140023f26  jz      loc_140023FD1
0x140023f2c  lea     rdx, byte_14000B36B
0x140023f33  jmp     short loc_140023F75
0x140023f35  mov     eax, cs:dword_14000E010
0x140023f3b  cmp     eax, 5
0x140023f3e  jbe     loc_140023FD1
0x140023f44  call    _tlgKeywordOn
0x140023f49  test    al, al
0x140023f4b  jz      loc_140023FD1
0x140023f51  lea     rdx, byte_14000B311
0x140023f58  jmp     short loc_140023F75
0x140023f5a  mov     eax, cs:dword_14000E010
0x140023f60  cmp     eax, 5
0x140023f63  jbe     short loc_140023FD1
0x140023f65  call    _tlgKeywordOn
0x140023f6a  test    al, al
0x140023f6c  jz      short loc_140023FD1
0x140023f6e  lea     rdx, word_14000B3CA; int
0x140023f75  lea     rax, [rbp+50h+var_68]
0x140023f79  mov     [rbp+50h+var_78], 2
0x140023f81  mov     [rbp+50h+var_80], rax
0x140023f85  mov     ecx, 0FFFFFFFEh; int
0x140023f8a  movzx   eax, word ptr [rsp+150h+var_108]
0x140023f8f  and     eax, ecx
0x140023f91  mov     [rbp+50h+var_70], r15
0x140023f95  mov     [rbp+50h+var_68], eax
0x140023f98  lea     rax, [rbp+50h+var_48]
0x140023f9c  mov     [rbp+50h+var_60], rax
0x140023fa0  mov     rax, qword ptr [rsp+150h+var_118+8]
0x140023fa5  mov     [rbp+50h+var_50], rax
0x140023fa9  movzx   eax, word ptr [rsp+150h+var_118]
0x140023fae  and     eax, ecx
0x140023fb0  mov     [rbp+50h+var_64], r14d
0x140023fb4  mov     [rbp+50h+var_48], eax
0x140023fb7  lea     rax, [rbp+50h+var_A0]
0x140023fbb  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x140023fc0  mov     [rbp+50h+var_58], 2
0x140023fc8  mov     [rbp+50h+var_44], r14d
0x140023fcc  call    _tlgWriteTransfer_EtwWriteTransfer
0x140023fd1  test    bl, bl
0x140023fd3  jz      short loc_140023FDF
0x140023fd5  mov     rcx, qword ptr [rsp+150h+var_F0+8]
0x140023fda  call    LuafvFreePool
0x140023fdf  mov     eax, [rsp+150h+var_120]
0x140023fe3  mov     rcx, [rbp+50h+var_40]
0x140023fe7  xor     rcx, rsp; StackCookie
0x140023fea  call    __security_check_cookie
0x140023fef  add     rsp, 120h
0x140023ff6  pop     r15
0x140023ff8  pop     r14
0x140023ffa  pop     r12
0x140023ffc  pop     rdi
0x140023ffd  pop     rsi
0x140023ffe  pop     rbx
0x140023fff  pop     rbp
0x140024000  retn
```
