# DiscpCreateDiscoveredTarget2

- ea: `0x180008e84`
- end: `0x180009350`
- name: `DiscpCreateDiscoveredTarget2`
- size: `1228`
- prototype: `__int64 __fastcall(void **, unsigned int *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009618`

## callees

- `0x180001cfe`
- `0x180005d2c`
- `0x180008e84`
- `0x18001048c`
- `0x180018f24`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpValidateiSCSIString` at `0x180008f62`
- `ISCSIUM!DiscpValidateiSCSIString` at `0x180008f62`
- `ISCSIUM!DiscpTextAddrToBinary` at `0x1800091c1`
- `ISCSIUM!DiscpTextAddrToBinary` at `0x1800091c1`
- `ISCSIUM!DiscpAllocMemory` at `0x180008fae`
- `ISCSIUM!DiscpAllocMemory` at `0x18000906d`
- `ISCSIUM!DiscpAllocMemory` at `0x180009181`
- `ISCSIUM!DiscpAllocMemory` at `0x180008fae`
- `ISCSIUM!DiscpAllocMemory` at `0x18000906d`
- `ISCSIUM!DiscpAllocMemory` at `0x180009181`
- `ISCSIUM!DiscpCopyString` at `0x180008f46`
- `ISCSIUM!DiscpCopyString` at `0x180008f97`
- `ISCSIUM!DiscpCopyString` at `0x180009241`
- `ISCSIUM!DiscpCopyString` at `0x180008f46`
- `ISCSIUM!DiscpCopyString` at `0x180008f97`
- `ISCSIUM!DiscpCopyString` at `0x180009241`
- `ISCSIUM!DiscpFreeMemory` at `0x18000921c`
- `ISCSIUM!DiscpFreeMemory` at `0x1800092de`
- `ISCSIUM!DiscpFreeMemory` at `0x1800092ed`
- `ISCSIUM!DiscpFreeMemory` at `0x18000930a`
- `ISCSIUM!DiscpFreeMemory` at `0x180009319`
- `ISCSIUM!DiscpFreeMemory` at `0x18000921c`
- `ISCSIUM!DiscpFreeMemory` at `0x1800092de`
- `ISCSIUM!DiscpFreeMemory` at `0x1800092ed`
- `ISCSIUM!DiscpFreeMemory` at `0x18000930a`
- `ISCSIUM!DiscpFreeMemory` at `0x180009319`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008ef9`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008ffa`
- `ISCSIUM!DiscpAlignDataStruct` at `0x1800090b5`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180009103`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008ef9`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008ffa`
- `ISCSIUM!DiscpAlignDataStruct` at `0x1800090b5`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180009103`

## pseudocode

```c
__int64 __fastcall DiscpCreateDiscoveredTarget2(void **a1, unsigned int *a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // eax
  unsigned int v5; // r15d
  __int64 v6; // rdx
  _DWORD *v7; // rax
  unsigned int v8; // esi
  __int64 v9; // r14
  unsigned int Target; // ebx
  void *v11; // rax
  unsigned int v12; // r13d
  unsigned int v13; // eax
  unsigned int v14; // edx
  __int64 v15; // rdi
  __int16 *v16; // rcx
  __int16 v17; // bx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r12
  __int64 v21; // rbx
  __int64 v22; // rdx
  unsigned int *v23; // rcx
  __int64 v24; // r15
  void *v25; // rax
  void *v26; // rdi
  __int64 v27; // r9
  char *v28; // rcx
  int v29; // eax
  unsigned int i; // edi
  __int64 v31; // rcx
  int v33; // [rsp+48h] [rbp-89h]
  unsigned int v34; // [rsp+68h] [rbp-69h] BYREF
  void *Src; // [rsp+70h] [rbp-61h] BYREF
  int v36; // [rsp+78h] [rbp-59h] BYREF
  int v37; // [rsp+7Ch] [rbp-55h]
  unsigned int v38; // [rsp+80h] [rbp-51h]
  _WORD *v39; // [rsp+88h] [rbp-49h] BYREF
  __int64 v40; // [rsp+90h] [rbp-41h] BYREF
  __int64 v41; // [rsp+98h] [rbp-39h] BYREF
  unsigned int v42; // [rsp+A0h] [rbp-31h]
  unsigned int v43; // [rsp+A4h] [rbp-2Dh]
  _DWORD *v44; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-19h]
  _DWORD v46[26]; // [rsp+C0h] [rbp-11h] BYREF

  v4 = *a2;
  v5 = 0;
  v6 = *(_QWORD *)(a3 + 40);
  v34 = v4;
  v7 = *a1;
  v8 = 0;
  v45 = v6;
  memset(v46, 0, 28);
  v39 = 0;
  v41 = 0;
  v40 = 0;
  v9 = 0;
  v36 = 0;
  v44 = v7;
  Src = v7;
  if ( (unsigned int)DiscpAlignDataStruct(&v44, &v34, 4)
    || (Src = v44, v34 <= 4)
    || (v8 = *v44, v34 -= 4, Src = v44 + 1, v39 = 0, (unsigned int)DiscpCopyString(&v39, &v36, &Src, 224, &v34))
    || !*v39
    || (unsigned int)DiscpValidateiSCSIString()
    || !v8
    || (v41 = 0, (Target = DiscpCopyString(&v41, &v36, &Src, 255, &v34)) != 0) )
  {
LABEL_43:
    Target = -268500967;
  }
  else
  {
    v11 = (void *)DiscpAllocMemory(8 * v8);
    v9 = (__int64)v11;
    if ( v11 )
    {
      memset_0(v11, 0, 8LL * v8);
      v37 = 0;
      v12 = 0;
      while ( !Target )
      {
        Target = DiscpAlignDataStruct(&Src, &v34, 4);
        if ( !Target )
        {
          v13 = v34;
          if ( v34 < 4 )
            goto LABEL_43;
          v14 = v34 - 4;
          v15 = *(unsigned int *)Src;
          v16 = (__int16 *)((char *)Src + 4);
          v43 = *(_DWORD *)Src;
          Src = (char *)Src + 4;
          v34 -= 4;
          if ( v13 - 4 < 2 )
            goto LABEL_43;
          v17 = *v16;
          Src = v16 + 1;
          v34 = v14 - 2;
          if ( !(_DWORD)v15 )
            goto LABEL_43;
          if ( (unsigned __int64)(1026 * v15) > 0xFFFFFFFF )
            goto LABEL_43;
          v18 = (unsigned int)(1026 * v15 + 8);
          if ( (unsigned int)v18 < 8 )
            goto LABEL_43;
          v19 = DiscpAllocMemory(v18);
          v20 = v19;
          if ( v19 )
          {
            v38 = 0;
            *(_QWORD *)(v9 + 8LL * v12) = v19;
            *(_WORD *)(v19 + 6) = v17;
            *(_DWORD *)v19 = v15;
            *(_BYTE *)(v19 + 4) = 1;
            Target = 0;
            do
            {
              if ( Target )
                break;
              if ( (unsigned int)DiscpAlignDataStruct(&Src, &v34, 4) )
                goto LABEL_43;
              if ( v34 < 2 )
                goto LABEL_43;
              v21 = v20 + 1026LL * v5 + 8;
              *(_WORD *)(v21 + 1024) = *(_WORD *)Src;
              Src = (char *)Src + 2;
              v34 -= 2;
              if ( (unsigned int)DiscpAlignDataStruct(&Src, &v34, 4) )
                goto LABEL_43;
              v40 = v21 + 512;
              DiscpGetIPAddressFromDataBlock(&v40, &Src, &v34, 256);
              if ( v34 < 4 )
                goto LABEL_43;
              v22 = v34 - 4;
              v42 = *(_DWORD *)Src;
              v23 = (unsigned int *)((char *)Src + 4);
              v34 -= 4;
              Src = (char *)Src + 4;
              if ( v34 < 4 )
                goto LABEL_43;
              v24 = *v23;
              Src = v23 + 1;
              v34 = v22 - 4;
              if ( (_DWORD)v24 )
              {
                v25 = (void *)DiscpAllocMemory((unsigned int)v24);
                v26 = v25;
                if ( !v25 || v34 < (unsigned int)v24 )
                  goto LABEL_43;
                memcpy_0(v25, Src, (unsigned int)v24);
                Src = (char *)Src + v24;
                v34 -= v24;
              }
              else
              {
                v26 = 0;
              }
              LOBYTE(v22) = 1;
              if ( !(unsigned int)DiscpTextAddrToBinary(v21 + 512, v22, v46) )
              {
                if ( v46[0] )
                {
                  LOBYTE(v27) = 5;
                  v28 = (char *)&v46[3];
                  v29 = 16;
                }
                else
                {
                  LOBYTE(v27) = 1;
                  v28 = (char *)&v46[1];
                  v29 = 4;
                }
                LOBYTE(v33) = 0;
                DiscpSetPresharedKey(a3, 0xFFFFFFFFLL, v42, v27, v29, v28, v24, v26, v33);
              }
              if ( v26 )
                DiscpFreeMemory(v26);
              v40 = v21;
              Target = DiscpCopyString(&v40, &v36, &Src, 256, &v34);
              v5 = v38 + 1;
              v38 = v5;
            }
            while ( v5 < v43 );
            v12 = v37;
            v5 = 0;
          }
          else
          {
            Target = 8;
          }
        }
        v37 = ++v12;
        if ( v12 >= v8 )
        {
          if ( !Target )
            Target = DiscpCreateTarget((_DWORD)v39, v41, v45, 0, 0, 0, v8, v9, *(_DWORD *)(a3 + 32), 5, a4);
          break;
        }
      }
    }
    else
    {
      Target = 8;
    }
  }
  if ( v39 )
    DiscpFreeMemory(v39);
  if ( v41 )
    DiscpFreeMemory(v41);
  if ( v9 )
  {
    for ( i = 0; i < v8; ++i )
    {
      v31 = *(_QWORD *)(v9 + 8LL * i);
      if ( v31 )
        DiscpFreeMemory(v31);
    }
    DiscpFreeMemory(v9);
  }
  *a1 = Src;
  *a2 = v34;
  return Target;
}

```

## disassembly

```asm
0x180008e84  mov     rax, rsp
0x180008e87  mov     [rax+20h], r9
0x180008e8b  mov     [rax+18h], r8
0x180008e8f  mov     [rax+10h], rdx
0x180008e93  mov     [rax+8], rcx
0x180008e97  push    rbp
0x180008e98  push    rbx
0x180008e99  push    rsi
0x180008e9a  push    rdi
0x180008e9b  push    r12
0x180008e9d  push    r13
0x180008e9f  push    r14
0x180008ea1  push    r15
0x180008ea3  lea     rbp, [rax-5Fh]
0x180008ea7  sub     rsp, 0E8h
0x180008eae  mov     eax, [rdx]
0x180008eb0  xor     r15d, r15d
0x180008eb3  mov     rdx, [r8+28h]
0x180008eb7  xorps   xmm0, xmm0
0x180008eba  mov     [rbp+57h+var_C0], eax
0x180008ebd  mov     rdi, r8
0x180008ec0  mov     rax, [rcx]
0x180008ec3  mov     esi, r15d
0x180008ec6  mov     [rbp+57h+var_70], rdx
0x180008eca  lea     r8d, [r15+4]
0x180008ece  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180008ed2  lea     rdx, [rbp+57h+var_C0]
0x180008ed6  mov     [rbp+57h+var_A0], r15
0x180008eda  lea     rcx, [rbp+57h+var_80]
0x180008ede  mov     [rbp+57h+var_90], r15
0x180008ee2  mov     [rbp+57h+var_98], r15
0x180008ee6  mov     r14d, r15d
0x180008ee9  mov     [rbp+57h+var_B0], r15d
0x180008eed  movups  xmmword ptr [rbp+57h+var_68+0Ch], xmm0
0x180008ef1  mov     [rbp+57h+var_80], rax
0x180008ef5  mov     [rbp+57h+Src], rax
0x180008ef9  call    cs:__imp_DiscpAlignDataStruct
0x180008eff  test    eax, eax
0x180008f01  jnz     loc_1800092D0
0x180008f07  cmp     [rbp+57h+var_C0], 4
0x180008f0b  mov     rcx, [rbp+57h+var_80]
0x180008f0f  mov     [rbp+57h+Src], rcx
0x180008f13  jbe     loc_1800092D0
0x180008f19  mov     esi, [rcx]
0x180008f1b  lea     rax, [rcx+4]
0x180008f1f  add     [rbp+57h+var_C0], 0FFFFFFFCh
0x180008f23  lea     r8, [rbp+57h+Src]
0x180008f27  mov     [rbp+57h+Src], rax
0x180008f2b  lea     rdx, [rbp+57h+var_B0]
0x180008f2f  lea     rax, [rbp+57h+var_C0]
0x180008f33  mov     [rbp+57h+var_A0], r15
0x180008f37  mov     r9d, 0E0h
0x180008f3d  mov     [rsp+120h+var_100], rax
0x180008f42  lea     rcx, [rbp+57h+var_A0]
0x180008f46  call    cs:__imp_DiscpCopyString
0x180008f4c  test    eax, eax
0x180008f4e  jnz     loc_1800092D0
0x180008f54  mov     rcx, [rbp+57h+var_A0]
0x180008f58  cmp     [rcx], r15w
0x180008f5c  jz      loc_1800092D0
0x180008f62  call    cs:__imp_DiscpValidateiSCSIString
0x180008f68  test    eax, eax
0x180008f6a  jnz     loc_1800092D0
0x180008f70  test    esi, esi
0x180008f72  jz      loc_1800092D0
0x180008f78  lea     rax, [rbp+57h+var_C0]
0x180008f7c  mov     [rbp+57h+var_90], r15
0x180008f80  mov     r9d, 0FFh
0x180008f86  mov     [rsp+120h+var_100], rax
0x180008f8b  lea     r8, [rbp+57h+Src]
0x180008f8f  lea     rdx, [rbp+57h+var_B0]
0x180008f93  lea     rcx, [rbp+57h+var_90]
0x180008f97  call    cs:__imp_DiscpCopyString
0x180008f9d  mov     ebx, eax
0x180008f9f  test    eax, eax
0x180008fa1  jnz     loc_1800092D0
0x180008fa7  lea     ecx, ds:0[rsi*8]
0x180008fae  call    cs:__imp_DiscpAllocMemory
0x180008fb4  mov     r14, rax
0x180008fb7  test    rax, rax
0x180008fba  jz      loc_180009349
0x180008fc0  mov     r8d, esi
0x180008fc3  xor     edx, edx; Val
0x180008fc5  shl     r8, 3; Size
0x180008fc9  mov     rcx, rax; void *
0x180008fcc  call    memset_0
0x180008fd1  mov     [rbp+57h+var_AC], r15d
0x180008fd5  mov     r13d, r15d
0x180008fd8  test    esi, esi
0x180008fda  jz      loc_180009283
0x180008fe0  mov     r12d, 0FFFFFFFFh
0x180008fe6  test    ebx, ebx
0x180008fe8  jnz     loc_1800092D5
0x180008fee  lea     r8d, [rbx+4]
0x180008ff2  lea     rdx, [rbp+57h+var_C0]
0x180008ff6  lea     rcx, [rbp+57h+Src]
0x180008ffa  call    cs:__imp_DiscpAlignDataStruct
0x180009000  mov     ebx, eax
0x180009002  test    eax, eax
0x180009004  jnz     loc_18000926B
0x18000900a  mov     eax, [rbp+57h+var_C0]
0x18000900d  cmp     eax, 4
0x180009010  jb      loc_1800092D0
0x180009016  mov     rcx, [rbp+57h+Src]
0x18000901a  add     eax, 0FFFFFFFCh
0x18000901d  mov     edx, eax
0x18000901f  mov     edi, [rcx]
0x180009021  add     rcx, 4
0x180009025  mov     [rbp+57h+var_84], edi
0x180009028  mov     [rbp+57h+Src], rcx
0x18000902c  mov     [rbp+57h+var_C0], eax
0x18000902f  cmp     eax, 2
0x180009032  jb      loc_1800092D0
0x180009038  movzx   ebx, word ptr [rcx]
0x18000903b  lea     rax, [rcx+2]
0x18000903f  mov     [rbp+57h+Src], rax
0x180009043  lea     eax, [rdx-2]
0x180009046  mov     [rbp+57h+var_C0], eax
0x180009049  test    edi, edi
0x18000904b  jz      loc_1800092D0
0x180009051  imul    rcx, rdi, 402h
0x180009058  cmp     rcx, r12
0x18000905b  ja      loc_1800092D0
0x180009061  add     ecx, 8
0x180009064  cmp     ecx, 8
0x180009067  jb      loc_1800092D0
0x18000906d  call    cs:__imp_DiscpAllocMemory
0x180009073  mov     r12, rax
0x180009076  test    rax, rax
0x180009079  jz      loc_1800092C6
0x18000907f  mov     ecx, r13d
0x180009082  mov     [rbp+57h+var_A8], r15d
0x180009086  mov     [r14+rcx*8], rax
0x18000908a  mov     [rax+6], bx
0x18000908e  xor     ebx, ebx
0x180009090  mov     [rax], edi
0x180009092  mov     byte ptr [rax+4], 1
0x180009096  test    edi, edi
0x180009098  jz      loc_180009262
0x18000909e  mov     ebx, r15d
0x1800090a1  test    ebx, ebx
0x1800090a3  jnz     loc_18000925E
0x1800090a9  lea     r8d, [rbx+4]
0x1800090ad  lea     rdx, [rbp+57h+var_C0]
0x1800090b1  lea     rcx, [rbp+57h+Src]
0x1800090b5  call    cs:__imp_DiscpAlignDataStruct
0x1800090bb  test    eax, eax
0x1800090bd  jnz     loc_1800092CD
0x1800090c3  cmp     [rbp+57h+var_C0], 2
0x1800090c7  jb      loc_1800092CD
0x1800090cd  mov     eax, r15d
0x1800090d0  lea     rdx, [rbp+57h+var_C0]
0x1800090d4  imul    rbx, rax, 402h
0x1800090db  mov     rax, [rbp+57h+Src]
0x1800090df  mov     r8d, 4
0x1800090e5  add     rbx, 8
0x1800090e9  add     rbx, r12
0x1800090ec  movzx   ecx, word ptr [rax]
0x1800090ef  mov     [rbx+400h], cx
0x1800090f6  lea     rcx, [rbp+57h+Src]
0x1800090fa  add     [rbp+57h+Src], 2
0x1800090ff  add     [rbp+57h+var_C0], 0FFFFFFFEh
0x180009103  call    cs:__imp_DiscpAlignDataStruct
0x180009109  xor     r15d, r15d
0x18000910c  test    eax, eax
0x18000910e  jnz     loc_1800092D0
0x180009114  lea     r13, [rbx+200h]
0x18000911b  mov     r9d, 100h
0x180009121  lea     r8, [rbp+57h+var_C0]
0x180009125  mov     [rbp+57h+var_98], r13
0x180009129  lea     rdx, [rbp+57h+Src]
0x18000912d  lea     rcx, [rbp+57h+var_98]
0x180009131  call    DiscpGetIPAddressFromDataBlock
0x180009136  mov     eax, [rbp+57h+var_C0]
0x180009139  cmp     eax, 4
0x18000913c  jb      loc_1800092D0
0x180009142  mov     rcx, [rbp+57h+Src]
0x180009146  add     eax, 0FFFFFFFCh
0x180009149  mov     edx, eax
0x18000914b  mov     ecx, [rcx]
0x18000914d  mov     [rbp+57h+var_88], ecx
0x180009150  mov     rcx, [rbp+57h+Src]
0x180009154  add     rcx, 4
0x180009158  mov     [rbp+57h+var_C0], eax
0x18000915b  mov     [rbp+57h+Src], rcx
0x18000915f  cmp     eax, 4
0x180009162  jb      loc_1800092D0
0x180009168  mov     r15d, [rcx]
0x18000916b  lea     rax, [rcx+4]
0x18000916f  mov     [rbp+57h+Src], rax
0x180009173  lea     eax, [rdx-4]
0x180009176  mov     [rbp+57h+var_C0], eax
0x180009179  test    r15d, r15d
0x18000917c  jz      short loc_1800091B6
0x18000917e  mov     ecx, r15d
0x180009181  call    cs:__imp_DiscpAllocMemory
0x180009187  mov     rdi, rax
0x18000918a  test    rax, rax
0x18000918d  jz      loc_1800092CD
0x180009193  cmp     [rbp+57h+var_C0], r15d
0x180009197  jb      loc_1800092CD
0x18000919d  mov     rdx, [rbp+57h+Src]; Src
0x1800091a1  mov     r8d, r15d; Size
0x1800091a4  mov     rcx, rax; void *
0x1800091a7  call    memcpy_0
0x1800091ac  add     [rbp+57h+Src], r15
0x1800091b0  sub     [rbp+57h+var_C0], r15d
0x1800091b4  jmp     short loc_1800091B8
0x1800091b6  xor     edi, edi
0x1800091b8  lea     r8, [rbp+57h+var_68]
0x1800091bc  mov     dl, 1
0x1800091be  mov     rcx, r13
0x1800091c1  call    cs:__imp_DiscpTextAddrToBinary
0x1800091c7  test    eax, eax
0x1800091c9  jnz     short loc_180009214
0x1800091cb  cmp     [rbp+57h+var_68], eax
0x1800091ce  jnz     short loc_1800091DE
0x1800091d0  mov     r9b, 1
0x1800091d3  lea     rcx, [rbp+57h+var_68+4]
0x1800091d7  mov     eax, 4
0x1800091dc  jmp     short loc_1800091EA
0x1800091de  mov     r9b, 5
0x1800091e1  lea     rcx, [rbp+57h+var_68+0Ch]
0x1800091e5  mov     eax, 10h
0x1800091ea  mov     r8d, [rbp+57h+var_88]
0x1800091ee  mov     edx, 0FFFFFFFFh
0x1800091f3  mov     byte ptr [rsp+120h+var_E0], 0
0x1800091f8  mov     qword ptr [rsp+120h+var_E8], rdi
0x1800091fd  mov     dword ptr [rsp+120h+var_F0], r15d
0x180009202  mov     qword ptr [rsp+120h+var_F8], rcx
0x180009207  mov     rcx, [rbp+57h+arg_10]
0x18000920b  mov     dword ptr [rsp+120h+var_100], eax
0x18000920f  call    DiscpSetPresharedKey
0x180009214  test    rdi, rdi
0x180009217  jz      short loc_180009222
0x180009219  mov     rcx, rdi
0x18000921c  call    cs:__imp_DiscpFreeMemory
0x180009222  lea     rax, [rbp+57h+var_C0]
0x180009226  mov     [rbp+57h+var_98], rbx
0x18000922a  mov     r9d, 100h
0x180009230  mov     [rsp+120h+var_100], rax
0x180009235  lea     r8, [rbp+57h+Src]
0x180009239  lea     rdx, [rbp+57h+var_B0]
0x18000923d  lea     rcx, [rbp+57h+var_98]
0x180009241  call    cs:__imp_DiscpCopyString
0x180009247  mov     r15d, [rbp+57h+var_A8]
0x18000924b  mov     ebx, eax
0x18000924d  inc     r15d
0x180009250  mov     [rbp+57h+var_A8], r15d
0x180009254  cmp     r15d, [rbp+57h+var_84]
0x180009258  jb      loc_1800090A1
0x18000925e  mov     r13d, [rbp+57h+var_AC]
0x180009262  xor     r15d, r15d
0x180009265  mov     r12d, 0FFFFFFFFh
0x18000926b  inc     r13d
0x18000926e  mov     [rbp+57h+var_AC], r13d
0x180009272  cmp     r13d, esi
0x180009275  jb      loc_180008FE6
0x18000927b  test    ebx, ebx
0x18000927d  jnz     short loc_1800092D5
0x18000927f  mov     rdi, [rbp+57h+arg_10]
0x180009283  mov     rax, [rbp+57h+arg_18]
0x180009287  xor     r9d, r9d
0x18000928a  mov     r8, [rbp+57h+var_70]
0x18000928e  mov     rdx, [rbp+57h+var_90]
0x180009292  mov     rcx, [rbp+57h+var_A0]
0x180009296  mov     [rsp+50h], rax
0x18000929b  mov     eax, [rdi+20h]
0x18000929e  mov     dword ptr [rsp+120h+var_D8], 5
0x1800092a6  mov     [rsp+120h+var_E0], eax
0x1800092aa  mov     qword ptr [rsp+120h+var_E8], r14
0x1800092af  mov     dword ptr [rsp+120h+var_F0], esi
0x1800092b3  mov     [rsp+120h+var_F8], r15d
0x1800092b8  mov     [rsp+120h+var_100], r15
0x1800092bd  call    DiscpCreateTarget
0x1800092c2  mov     ebx, eax
0x1800092c4  jmp     short loc_1800092D5
0x1800092c6  mov     ebx, 8
0x1800092cb  jmp     short loc_180009265
0x1800092cd  xor     r15d, r15d
0x1800092d0  mov     ebx, 0EFFF0019h
0x1800092d5  mov     rcx, [rbp+57h+var_A0]
0x1800092d9  test    rcx, rcx
0x1800092dc  jz      short loc_1800092E4
0x1800092de  call    cs:__imp_DiscpFreeMemory
0x1800092e4  mov     rcx, [rbp+57h+var_90]
0x1800092e8  test    rcx, rcx
0x1800092eb  jz      short loc_1800092F3
0x1800092ed  call    cs:__imp_DiscpFreeMemory
0x1800092f3  test    r14, r14
0x1800092f6  jz      short loc_18000931F
0x1800092f8  mov     edi, r15d
0x1800092fb  test    esi, esi
0x1800092fd  jz      short loc_180009316
0x1800092ff  mov     eax, edi
0x180009301  mov     rcx, [r14+rax*8]
0x180009305  test    rcx, rcx
0x180009308  jz      short loc_180009310
0x18000930a  call    cs:__imp_DiscpFreeMemory
0x180009310  inc     edi
  ... truncated ...
```
