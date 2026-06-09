# LdrResGetRCConfig

- ea: `0x1800a5610`
- end: `0x1800a5b41`
- name: `LdrResGetRCConfig`
- size: `1329`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180059200`
- `0x18005c73c`
- `0x1800a2a90`
- `0x1800a2b20`
- `0x1800a52a0`

## callees

- `0x1800526f0`
- `0x180056330`
- `0x180056b70`
- `0x1800a2b20`
- `0x1800a5610`
- `0x1800a5b48`
- `0x1800a5c30`
- `0x1800a6c7c`
- `0x180162000`

## string_xrefs

- `0x1800a56a4`: `LdrResGetRCConfig Exit`
- `0x1800a5691`: `LdrResGetRCConfig Enter`

## pseudocode

```c
__int64 __fastcall LdrResGetRCConfig(__int64 a1, __int64 a2, __int64 *a3, __int64 a4, char a5)
{
  unsigned int v5; // r10d
  __int64 *v6; // r13
  __int64 v7; // rdi
  _DWORD *SharedData; // rcx
  unsigned __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r15
  __int64 v13; // rax
  int v14; // edi
  _DWORD *v15; // rax
  __int64 result; // rax
  __int64 v17; // rcx
  int v18; // r13d
  int v19; // r8d
  int v20; // eax
  __int64 v21; // rcx
  char v22; // al
  int v23; // r9d
  __int64 *v24; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+60h] [rbp-A8h]
  __int64 v26; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+70h] [rbp-98h]
  __int64 v28; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v29[2]; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v30[2]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD *v31; // [rsp+A0h] [rbp-68h]
  __int64 v32; // [rsp+A8h] [rbp-60h]
  _QWORD v33[3]; // [rsp+B0h] [rbp-58h] BYREF

  v5 = a4;
  v25 = a4;
  v6 = a3;
  v31 = a3;
  v7 = a2;
  v27 = a2;
  v32 = a1;
  v33[0] = L"MUI";
  v33[1] = 1;
  v33[2] = 0;
  v28 = 0;
  v26 = a2;
  v24 = 0;
  v29[0] = 3145774;
  v29[1] = L"LdrResGetRCConfig Enter";
  v30[0] = 3014700;
  v30[1] = L"LdrResGetRCConfig Exit";
  SharedData = NtCurrentPeb()->SharedData;
  if ( SharedData && *SharedData )
  {
    v10 = (unsigned __int64)NtCurrentPeb()->SharedData + 555;
    v11 = 2147353477;
  }
  else
  {
    v11 = 2147353477;
    v10 = 2147353477;
  }
  if ( (*(_BYTE *)v10 & 1) != 0 )
  {
    v12 = 2147353476;
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v10, a2, a3, a4) )
      v17 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v17 = 2147353476;
    LdrpTraceLoadMUIDll(v29, *(unsigned __int8 *)v17);
    v5 = v25;
  }
  else
  {
    v12 = 2147353476;
  }
  if ( a1 )
  {
    if ( a5 )
    {
      v13 = LdrpGetFromMUIMemCache(a1, 0, 0, 8);
      v24 = (__int64 *)v13;
      if ( v13 == -1 )
      {
        v14 = -1073741686;
        goto LABEL_10;
      }
      if ( v13 )
      {
        v14 = 0;
        if ( v6 )
          *v6 = v13;
        goto LABEL_10;
      }
      v5 = v25;
    }
    v18 = v5 & 0x2000;
    if ( !v7 && (v5 & 0x2000) == 0 )
    {
      result = LdrpResGetMappingSize(a1, &v26, v5, 0);
      if ( (int)result < 0 )
        return result;
      LODWORD(v7) = v26;
      v27 = v26;
    }
    v19 = 4144;
    if ( v18 )
      v19 = 8240;
    v20 = LdrpResSearchResourceMappedFile(a1, v7, v19, (unsigned int)v33, 3, (__int64)&v24, (__int64)&v28, 0, 0);
    v14 = v20;
    if ( v20 < 0 )
    {
      if ( v20 != -1073741701 )
      {
        v14 = -1073741686;
LABEL_77:
        a3 = 0;
        v24 = 0;
LABEL_78:
        if ( a5 )
        {
          v23 = -1;
          if ( a3 )
            v23 = (int)a3;
          LdrpSetAlternateResourceModuleHandle(a1, 0, 0, v23, 0, 2, v14, 0);
        }
        goto LABEL_10;
      }
      a3 = v24;
    }
    else
    {
      a3 = v24;
      if ( v18 )
        goto LABEL_82;
      a2 = *((unsigned int *)v24 + 1);
      v10 = v27 + (a1 & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (unsigned __int64)v24 + a2 > v10 )
      {
        v14 = -1073741701;
        goto LABEL_76;
      }
      v14 = -1073020925;
      v10 = *((unsigned int *)v24 + 17);
      a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 18));
      if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
      {
        v10 = *((unsigned int *)v24 + 19);
        a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 20));
        if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
        {
          v10 = *((unsigned int *)v24 + 21);
          a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 22));
          if ( (unsigned int)a4 >= (unsigned int)v10 && (unsigned int)a4 <= (unsigned int)a2 )
          {
            v10 = *((unsigned int *)v24 + 23);
            a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 24));
            if ( (unsigned int)a4 >= (unsigned int)v10 && (unsigned int)a4 <= (unsigned int)a2 )
            {
              v10 = *((unsigned int *)v24 + 25);
              a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 26));
              if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
              {
                v10 = *((unsigned int *)v24 + 27);
                a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 28));
                if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
                {
                  v10 = *((unsigned int *)v24 + 29);
                  a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 30));
                  if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
                  {
                    v10 = *((unsigned int *)v24 + 31);
                    a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 32));
                    if ( (unsigned int)a4 <= (unsigned int)a2
                      && (unsigned int)a4 >= (unsigned int)v10
                      && *(_DWORD *)v24 == -20054323
                      && a2 == v28
                      && *((_DWORD *)v24 + 2) == 0x10000 )
                    {
                      v21 = *((unsigned int *)v24 + 3);
                      if ( !(_DWORD)v21 || (unsigned __int8)CheckOneBitValidFlag(v21, 7, v24) )
                      {
                        if ( (unsigned __int8)CheckOneBitValidFlag((_DWORD)a3[2] & 0xFFFFFFCF, 3, a3) )
                        {
                          if ( (unsigned __int8)CheckOneBitValidFlag((unsigned int)a4 & 0xFFFFFFFC, 48, a3) )
                          {
                            if ( (a4 & 1) == 0
                              || (unsigned __int8)CheckOneBitValidFlag(*((unsigned int *)a3 + 6), 3, a3)
                              && ((v10 = *((unsigned int *)a3 + 5), !(_DWORD)v10)
                               || (v22 = CheckOneBitValidFlag(v10, 256, a3)) != 0) )
                            {
LABEL_82:
                              if ( v31 )
                                *v31 = a3;
                              v14 = 0;
                              goto LABEL_78;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_76:
    if ( v14 >= 0 )
      goto LABEL_78;
    goto LABEL_77;
  }
  v14 = -1073741811;
LABEL_10:
  v15 = NtCurrentPeb()->SharedData;
  if ( v15 && *v15 )
    v11 = (__int64)NtCurrentPeb()->SharedData + 555;
  if ( (*(_BYTE *)v11 & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v10, a2, a3, a4) )
      v12 = (__int64)NtCurrentPeb()->SharedData + 554;
    LdrpTraceLoadMUIDll(v30, *(unsigned __int8 *)v12);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800a5610  mov     r11, rsp
0x1800a5613  push    rbx
0x1800a5614  push    rsi
0x1800a5615  push    rdi
0x1800a5616  push    r12
0x1800a5618  push    r13
0x1800a561a  push    r14
0x1800a561c  push    r15
0x1800a561e  sub     rsp, 0D0h
0x1800a5625  mov     rax, cs:__security_cookie
0x1800a562c  xor     rax, rsp
0x1800a562f  mov     [rsp+108h+var_40], rax
0x1800a5637  mov     r10d, r9d
0x1800a563a  mov     [rsp+108h+var_A8], r9d
0x1800a563f  mov     r13, r8
0x1800a5642  mov     [rsp+108h+var_68], r8
0x1800a564a  mov     rdi, rdx
0x1800a564d  mov     [rsp+108h+var_98], rdx
0x1800a5652  mov     r14, rcx
0x1800a5655  mov     [rsp+108h+var_60], rcx
0x1800a565d  lea     rax, aMui; "MUI"
0x1800a5664  mov     [r11-58h], rax
0x1800a5668  mov     qword ptr [r11-50h], 1
0x1800a5670  xor     r12d, r12d
0x1800a5673  mov     [r11-48h], r12
0x1800a5677  mov     [rsp+108h+var_90], r12
0x1800a567c  mov     [rsp+108h+var_A0], rdx
0x1800a5681  mov     [rsp+108h+var_B0], r12
0x1800a5686  mov     qword ptr [r11-88h], 30002Eh
0x1800a5691  lea     rax, aLdrresgetrccon_0; "LdrResGetRCConfig Enter"
0x1800a5698  mov     [r11-80h], rax
0x1800a569c  mov     qword ptr [r11-78h], 2E002Ch
0x1800a56a4  lea     rax, aLdrresgetrccon_1; "LdrResGetRCConfig Exit"
0x1800a56ab  mov     [r11-70h], rax
0x1800a56af  mov     rax, gs:60h
0x1800a56b8  mov     rcx, [rax+90h]
0x1800a56bf  test    rcx, rcx
0x1800a56c2  jz      loc_1800A579D
0x1800a56c8  cmp     [rcx], r12d
0x1800a56cb  jz      loc_1800A579D
0x1800a56d1  mov     rax, gs:60h
0x1800a56da  mov     rcx, [rax+90h]
0x1800a56e1  add     rcx, 22Bh
0x1800a56e8  mov     ebx, 7FFE0385h
0x1800a56ed  test    byte ptr [rcx], 1
0x1800a56f0  jnz     loc_1800A57A9
0x1800a56f6  mov     r15d, 7FFE0384h
0x1800a56fc  test    r14, r14
0x1800a56ff  jz      loc_1800A59F8
0x1800a5705  movzx   esi, [rsp+108h+arg_20]
0x1800a570d  test    sil, sil
0x1800a5710  jz      loc_1800A57F2
0x1800a5716  xor     edx, edx
0x1800a5718  mov     r9d, 8
0x1800a571e  xor     r8d, r8d
0x1800a5721  mov     rcx, r14
0x1800a5724  call    LdrpGetFromMUIMemCache
0x1800a5729  mov     [rsp+108h+var_B0], rax
0x1800a572e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5732  jnz     loc_1800A59DA
0x1800a5738  mov     edi, 0C000008Ah
0x1800a573d  mov     rax, gs:60h
0x1800a5746  mov     rax, [rax+90h]
0x1800a574d  test    rax, rax
0x1800a5750  jz      short loc_1800A576E
0x1800a5752  cmp     dword ptr [rax], 0
0x1800a5755  jz      short loc_1800A576E
0x1800a5757  mov     rax, gs:60h
0x1800a5760  mov     rbx, [rax+90h]
0x1800a5767  add     rbx, 22Bh
0x1800a576e  test    byte ptr [rbx], 1
0x1800a5771  jnz     loc_1800A5A02
0x1800a5777  mov     eax, edi
0x1800a5779  mov     rcx, [rsp+108h+var_40]
0x1800a5781  xor     rcx, rsp; StackCookie
0x1800a5784  call    __security_check_cookie
0x1800a5789  add     rsp, 0D0h
0x1800a5790  pop     r15
0x1800a5792  pop     r14
0x1800a5794  pop     r13
0x1800a5796  pop     r12
0x1800a5798  pop     rdi
0x1800a5799  pop     rsi
0x1800a579a  pop     rbx
0x1800a579b  retn
0x1800a579d  mov     ebx, 7FFE0385h
0x1800a57a2  mov     ecx, ebx
0x1800a57a4  jmp     loc_1800A56ED
0x1800a57a9  call    RtlGetCurrentServiceSessionId
0x1800a57ae  mov     r15d, 7FFE0384h
0x1800a57b4  test    eax, eax
0x1800a57b6  jz      loc_1800A5A38
0x1800a57bc  mov     rax, gs:60h
0x1800a57c5  mov     rcx, [rax+90h]
0x1800a57cc  add     rcx, 22Ah
0x1800a57d3  movzx   edx, byte ptr [rcx]
0x1800a57d6  lea     rcx, [rsp+108h+var_88]
0x1800a57de  call    LdrpTraceLoadMUIDll
0x1800a57e3  mov     r10d, [rsp+108h+var_A8]
0x1800a57e8  jmp     loc_1800A56FC
0x1800a57ed  mov     r10d, [rsp+108h+var_A8]
0x1800a57f2  mov     r13d, r10d
0x1800a57f5  and     r13d, 2000h
0x1800a57fc  test    rdi, rdi
0x1800a57ff  jnz     short loc_1800A582B
0x1800a5801  test    r13d, r13d
0x1800a5804  jnz     short loc_1800A582B
0x1800a5806  xor     r9d, r9d
0x1800a5809  mov     r8d, r10d
0x1800a580c  lea     rdx, [rsp+108h+var_A0]
0x1800a5811  mov     rcx, r14
0x1800a5814  call    LdrpResGetMappingSize
0x1800a5819  test    eax, eax
0x1800a581b  js      loc_1800A5779
0x1800a5821  mov     rdi, [rsp+108h+var_A0]
0x1800a5826  mov     [rsp+108h+var_98], rdi
0x1800a582b  mov     eax, 2030h
0x1800a5830  mov     r8d, 1030h
0x1800a5836  test    r13d, r13d
0x1800a5839  cmovnz  r8d, eax
0x1800a583d  mov     [rsp+108h+var_C8], r12
0x1800a5842  mov     [rsp+108h+var_D0], r12
0x1800a5847  lea     rax, [rsp+108h+var_90]
0x1800a584c  mov     [rsp+108h+var_D8], rax
0x1800a5851  lea     rax, [rsp+108h+var_B0]
0x1800a5856  mov     [rsp+108h+var_E0], rax
0x1800a585b  mov     [rsp+108h+var_E8], 3
0x1800a5863  lea     r9, [rsp+108h+var_58]
0x1800a586b  mov     rdx, rdi
0x1800a586e  mov     rcx, r14
0x1800a5871  call    LdrpResSearchResourceMappedFile
0x1800a5876  mov     edi, eax
0x1800a5878  test    eax, eax
0x1800a587a  js      loc_1800A5B27
0x1800a5880  mov     r8, [rsp+108h+var_B0]
0x1800a5885  test    r13d, r13d
0x1800a5888  jnz     loc_1800A5A9B
0x1800a588e  mov     edx, [r8+4]
0x1800a5892  mov     rcx, r14
0x1800a5895  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800a5899  add     rcx, [rsp+108h+var_98]
0x1800a589e  lea     rax, [rdx+r8]
0x1800a58a2  cmp     rax, rcx
0x1800a58a5  ja      loc_1800A5A40
0x1800a58ab  mov     edi, 0C00B0003h
0x1800a58b0  mov     [rsp+108h+var_B8], edi
0x1800a58b4  mov     ecx, [r8+44h]
0x1800a58b8  mov     r9d, [r8+48h]
0x1800a58bc  add     r9d, ecx
0x1800a58bf  cmp     r9d, edx
0x1800a58c2  ja      short loc_1800A5903
0x1800a58c4  cmp     r9d, ecx
0x1800a58c7  jb      short loc_1800A5903
0x1800a58c9  mov     ecx, [r8+4Ch]
0x1800a58cd  mov     r9d, [r8+50h]
0x1800a58d1  add     r9d, ecx
0x1800a58d4  cmp     r9d, edx
0x1800a58d7  ja      short loc_1800A5903
0x1800a58d9  cmp     r9d, ecx
0x1800a58dc  jb      short loc_1800A5903
0x1800a58de  mov     ecx, [r8+54h]
0x1800a58e2  mov     r9d, [r8+58h]
0x1800a58e6  add     r9d, ecx
0x1800a58e9  cmp     r9d, ecx
0x1800a58ec  jb      short loc_1800A5903
0x1800a58ee  cmp     r9d, edx
0x1800a58f1  ja      short loc_1800A5903
0x1800a58f3  mov     ecx, [r8+5Ch]
0x1800a58f7  mov     r9d, [r8+60h]
0x1800a58fb  add     r9d, ecx
0x1800a58fe  cmp     r9d, ecx
0x1800a5901  jnb     short loc_1800A5908
0x1800a5903  jmp     loc_1800A5AC9
0x1800a5908  cmp     r9d, edx
0x1800a590b  ja      short loc_1800A5903
0x1800a590d  mov     ecx, [r8+64h]
0x1800a5911  mov     r9d, [r8+68h]
0x1800a5915  add     r9d, ecx
0x1800a5918  cmp     r9d, edx
0x1800a591b  ja      short loc_1800A5903
0x1800a591d  cmp     r9d, ecx
0x1800a5920  jb      short loc_1800A5903
0x1800a5922  mov     ecx, [r8+6Ch]
0x1800a5926  mov     r9d, [r8+70h]
0x1800a592a  add     r9d, ecx
0x1800a592d  cmp     r9d, edx
0x1800a5930  ja      short loc_1800A5903
0x1800a5932  cmp     r9d, ecx
0x1800a5935  jb      short loc_1800A5903
0x1800a5937  mov     ecx, [r8+74h]
0x1800a593b  mov     r9d, [r8+78h]
0x1800a593f  add     r9d, ecx
0x1800a5942  cmp     r9d, edx
0x1800a5945  ja      short loc_1800A5903
0x1800a5947  cmp     r9d, ecx
0x1800a594a  jb      short loc_1800A5903
0x1800a594c  mov     ecx, [r8+7Ch]
0x1800a5950  mov     r9d, [r8+80h]
0x1800a5957  add     r9d, ecx
0x1800a595a  cmp     r9d, edx
0x1800a595d  ja      short loc_1800A5903
0x1800a595f  cmp     r9d, ecx
0x1800a5962  jb      short loc_1800A5903
0x1800a5964  cmp     dword ptr [r8], 0FECDFECDh
0x1800a596b  jnz     loc_1800A5A6B
0x1800a5971  cmp     rdx, [rsp+108h+var_90]
0x1800a5976  jnz     loc_1800A5A6B
0x1800a597c  cmp     dword ptr [r8+8], 10000h
0x1800a5984  jnz     loc_1800A5A6F
0x1800a598a  mov     ecx, [r8+0Ch]
0x1800a598e  test    ecx, ecx
0x1800a5990  jnz     loc_1800A5A71
0x1800a5996  mov     r9d, [r8+10h]
0x1800a599a  mov     ecx, r9d
0x1800a599d  and     ecx, 0FFFFFFCFh
0x1800a59a0  mov     edx, 3
0x1800a59a5  call    CheckOneBitValidFlag
0x1800a59aa  test    al, al
0x1800a59ac  jz      loc_1800A5A6D
0x1800a59b2  mov     ecx, r9d
0x1800a59b5  and     ecx, 0FFFFFFFCh
0x1800a59b8  mov     edx, 30h ; '0'
0x1800a59bd  call    CheckOneBitValidFlag
0x1800a59c2  test    al, al
0x1800a59c4  jz      loc_1800A5A6D
0x1800a59ca  test    r9b, 1
0x1800a59ce  jnz     short loc_1800A5A4B
0x1800a59d0  mov     [rsp+108h+var_B8], r12d
0x1800a59d5  jmp     loc_1800A5A9B
0x1800a59da  test    rax, rax
0x1800a59dd  jz      loc_1800A57ED
0x1800a59e3  mov     edi, r12d
0x1800a59e6  test    r13, r13
0x1800a59e9  jz      loc_1800A573D
0x1800a59ef  mov     [r13+0], rax
0x1800a59f3  jmp     loc_1800A573D
0x1800a59f8  mov     edi, 0C000000Dh
0x1800a59fd  jmp     loc_1800A573D
0x1800a5a02  call    RtlGetCurrentServiceSessionId
0x1800a5a07  test    eax, eax
0x1800a5a09  jz      short loc_1800A5A22
0x1800a5a0b  mov     rax, gs:60h
0x1800a5a14  mov     r15, [rax+90h]
0x1800a5a1b  add     r15, 22Ah
0x1800a5a22  movzx   edx, byte ptr [r15]
0x1800a5a26  lea     rcx, [rsp+108h+var_78]
0x1800a5a2e  call    LdrpTraceLoadMUIDll
0x1800a5a33  jmp     loc_1800A5777
0x1800a5a38  mov     rcx, r15
0x1800a5a3b  jmp     loc_1800A57D3
0x1800a5a40  mov     edi, 0C000007Bh
0x1800a5a45  mov     [rsp+108h+var_B8], edi
0x1800a5a49  jmp     short loc_1800A5AC9
0x1800a5a4b  mov     edx, 3
0x1800a5a50  mov     ecx, [r8+18h]
0x1800a5a54  call    CheckOneBitValidFlag
0x1800a5a59  test    al, al
0x1800a5a5b  jz      short loc_1800A5A85
0x1800a5a5d  mov     ecx, [r8+14h]
0x1800a5a61  test    ecx, ecx
0x1800a5a63  jz      loc_1800A59D0
0x1800a5a69  jmp     short loc_1800A5A87
0x1800a5a6b  jmp     short loc_1800A5AC9
0x1800a5a6d  jmp     short loc_1800A5AC9
0x1800a5a6f  jmp     short loc_1800A5AC9
0x1800a5a71  mov     edx, 7
0x1800a5a76  call    CheckOneBitValidFlag
0x1800a5a7b  test    al, al
0x1800a5a7d  jnz     loc_1800A5996
0x1800a5a83  jmp     short loc_1800A5AC9
0x1800a5a85  jmp     short loc_1800A5AC9
0x1800a5a87  mov     edx, 100h
0x1800a5a8c  call    CheckOneBitValidFlag
0x1800a5a91  test    al, al
0x1800a5a93  jnz     loc_1800A59D0
0x1800a5a99  jmp     short loc_1800A5AC9
0x1800a5a9b  jmp     short loc_1800A5B15
0x1800a5a9d  mov     edi, eax
0x1800a5a9f  mov     [rsp+108h+var_B8], eax
0x1800a5aa3  xor     r8d, r8d
0x1800a5aa6  mov     [rsp+108h+var_B0], r8
0x1800a5aab  xor     r12d, r12d
0x1800a5aae  mov     ebx, 7FFE0385h
0x1800a5ab3  mov     r15d, 7FFE0384h
0x1800a5ab9  movzx   esi, [rsp+108h+arg_20]
0x1800a5ac1  mov     r14, [rsp+108h+var_60]
0x1800a5ac9  test    edi, edi
0x1800a5acb  jns     short loc_1800A5AD5
0x1800a5acd  mov     r8, r12
0x1800a5ad0  mov     [rsp+108h+var_B0], r12
0x1800a5ad5  test    sil, sil
0x1800a5ad8  jz      loc_1800A573D
0x1800a5ade  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800a5ae5  test    r8, r8
0x1800a5ae8  cmovnz  r9, r8
0x1800a5aec  mov     [rsp+108h+var_D0], r12
0x1800a5af1  mov     dword ptr [rsp+108h+var_D8], edi
0x1800a5af5  mov     dword ptr [rsp+108h+var_E0], 2
0x1800a5afd  mov     word ptr [rsp+108h+var_E8], r12w
0x1800a5b03  xor     r8d, r8d
  ... truncated ...
```
