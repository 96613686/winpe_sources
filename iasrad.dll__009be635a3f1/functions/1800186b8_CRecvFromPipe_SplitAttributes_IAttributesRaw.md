# CRecvFromPipe::SplitAttributes(IAttributesRaw *)

- ea: `0x1800186b8`
- end: `0x180018b41`
- name: `?SplitAttributes@CRecvFromPipe@@AEAAJPEAUIAttributesRaw@@@Z`
- size: `1161`
- prototype: `__int64 __fastcall(CRecvFromPipe *__hidden this, struct IAttributesRaw *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800179a4`

## callees

- `0x1800094e4`
- `0x18000dc54`
- `0x1800181e8`
- `0x1800186b8`
- `0x18001d31c`
- `0x18002ae20`
- `0x18002af04`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002efa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002efa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800187e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800187e5`

## string_xrefs

- `0x180018abc`: `Unable to remove attribute from collectionwhile splitting out-bound attributes`

## pseudocode

```c
__int64 __fastcall CRecvFromPipe::SplitAttributes(CRecvFromPipe *this, struct IAttributesRaw *a2)
{
  unsigned int v3; // r13d
  LPVOID *v4; // r14
  int v5; // ebx
  __int64 v6; // rdx
  unsigned int i; // r15d
  LPVOID *v8; // r13
  _DWORD *v9; // rdx
  int v10; // edx
  __int64 v11; // r8
  int v12; // r13d
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int j; // edi
  unsigned int v18; // [rsp+30h] [rbp-48h]
  unsigned int v19; // [rsp+80h] [rbp+8h] BYREF
  int v20; // [rsp+84h] [rbp+Ch]
  LPVOID *v21; // [rsp+90h] [rbp+18h]

  v20 = HIDWORD(this);
  v3 = 0;
  v4 = 0;
  v19 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, unsigned int *))(*(_QWORD *)a2 + 48LL))(a2, &v19);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to obtain attribute count in request while splitting attributes in out-bound packet ");
      v6 = 47;
LABEL_6:
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  if ( !v19 )
    goto LABEL_62;
  if ( v19 > 0xFFFFFFF )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Large attribute count caused integer overflow");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
    }
    v5 = -2147024362;
    goto LABEL_62;
  }
  v4 = (LPVOID *)CoTaskMemAlloc(16LL * v19);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to allocate memory for attribute position array while splitting attributes in out-bound packet");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
    }
    v5 = -2147024882;
    goto LABEL_62;
  }
  v5 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, unsigned int *, LPVOID *, __int64, __int64 *))(*(_QWORD *)a2 + 56LL))(
         a2,
         &v19,
         v4,
         7,
         qword_180041518);
  if ( v5 >= 0 )
  {
    if ( !v19 )
      goto LABEL_62;
    v18 = v19;
    for ( i = 0; ; ++i )
    {
      if ( i >= v19 )
      {
LABEL_61:
        v3 = v18;
        goto LABEL_62;
      }
      v8 = &v4[2 * i];
      v21 = v8;
      v9 = v8[1];
      if ( (v9[1] & 7) != 0 )
      {
        v10 = v9[2];
        if ( ((unsigned int)(v10 - 8145) <= 1 || v10 == 4165 || v10 == 8150)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("The attribute with id: '%d' should no appear on the way out from the pipeline, /n since nps doesn'"
                      "t process NAP attributes");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids,
            (unsigned int)"NPSRAD",
            *((_DWORD *)v8[1] + 2));
        }
        v11 = (__int64)v8[1];
        v12 = *(_DWORD *)(v11 + 16);
        if ( v12 == 5 )
        {
          v13 = IASAttributeAnsiAlloc(v11);
          if ( v13 )
          {
            if ( v13 > 0 )
              v5 = (unsigned __int16)v13 | 0x80070000;
            else
              v5 = v13;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WppDbgPrint("Unable to allocate memory for string attribute while splitting attributes in out-bound packet");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                52,
                WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids,
                "NPSRAD");
            }
            goto LABEL_61;
          }
          v11 = (__int64)v21[1];
          v14 = -1;
          do
            ++v14;
          while ( *(_BYTE *)(*(_QWORD *)(v11 + 24) + v14) );
        }
        else
        {
          if ( v12 != 6 )
            continue;
          LODWORD(v14) = *(_DWORD *)(v11 + 24);
        }
        v15 = 247;
        if ( *(_DWORD *)(v11 + 8) <= 0xFFu )
          v15 = 253;
        if ( (unsigned int)v14 > (unsigned int)v15 )
        {
          v5 = CRecvFromPipe::SplitAndAdd(v15, (__int64)a2, v11, v12, v14, v15);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, __int64, LPVOID *))(*(_QWORD *)a2 + 32LL))(
                   a2,
                   1,
                   v21);
            if ( v5 < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WppDbgPrint("Unable to remove attribute from collectionwhile splitting out-bound attributes");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                53,
                WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids,
                "NPSRAD");
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Unable to obtain information about attributeswhile splitting attributes in out-bound RADIUS packet");
    v6 = 50;
    goto LABEL_6;
  }
LABEL_62:
  if ( v4 )
  {
    for ( j = 0; j < v3; ++j )
      IASAttributeRelease(v4[2 * j + 1]);
    CoTaskMemFree(v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800186b8  mov     r11, rsp
0x1800186bb  mov     [r11+10h], rbx
0x1800186bf  mov     [r11+20h], rsi
0x1800186c3  mov     [r11+8], rcx
0x1800186c7  push    rdi
0x1800186c8  push    r12
0x1800186ca  push    r13
0x1800186cc  push    r14
0x1800186ce  push    r15
0x1800186d0  sub     rsp, 50h
0x1800186d4  mov     r12, rdx
0x1800186d7  xor     r13d, r13d
0x1800186da  mov     [r11-48h], r13d
0x1800186de  xor     r14d, r14d
0x1800186e1  mov     [r11-38h], r14
0x1800186e5  mov     [r11+8], r14d
0x1800186e9  mov     rax, [rdx]
0x1800186ec  lea     rdx, [r11+8]
0x1800186f0  mov     rcx, r12
0x1800186f3  mov     rax, [rax+30h]
0x1800186f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186fc  mov     ebx, eax
0x1800186fe  mov     [rsp+78h+var_44], eax
0x180018702  test    eax, eax
0x180018704  jns     short loc_180018768
0x180018706  lea     rsi, WPP_GLOBAL_Control
0x18001870d  mov     rax, cs:WPP_GLOBAL_Control
0x180018714  cmp     rax, rsi
0x180018717  jz      loc_180018AFA
0x18001871d  cmp     byte ptr [rax+19h], 2
0x180018721  jb      loc_180018AFA
0x180018727  mov     edi, 100h
0x18001872c  test    [rax+1Ch], edi
0x18001872f  jz      loc_180018AFA
0x180018735  lea     rcx, aUnableToObtain_5; "Unable to obtain attribute count in req"...
0x18001873c  call    WppDbgPrint
0x180018741  lea     edx, [r13+2Fh]
0x180018745  lea     r9, aNpsrad; "NPSRAD"
0x18001874c  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180018753  mov     rcx, cs:WPP_GLOBAL_Control
0x18001875a  mov     rcx, [rcx+10h]
0x18001875e  call    WPP_SF_s
0x180018763  jmp     loc_180018AFA
0x180018768  mov     eax, [rsp+78h+arg_0]
0x18001876f  test    eax, eax
0x180018771  jz      loc_180018AFA
0x180018777  cmp     eax, 0FFFFFFFh
0x18001877c  jbe     short loc_1800187DE
0x18001877e  lea     rsi, WPP_GLOBAL_Control
0x180018785  mov     rax, cs:WPP_GLOBAL_Control
0x18001878c  cmp     rax, rsi
0x18001878f  jz      short loc_1800187D0
0x180018791  cmp     byte ptr [rax+19h], 2
0x180018795  jb      short loc_1800187D0
0x180018797  mov     edi, 100h
0x18001879c  test    [rax+1Ch], edi
0x18001879f  jz      short loc_1800187D0
0x1800187a1  lea     rcx, aLargeAttribute; "Large attribute count caused integer ov"...
0x1800187a8  call    WppDbgPrint
0x1800187ad  mov     edx, 30h ; '0'
0x1800187b2  lea     r9, aNpsrad; "NPSRAD"
0x1800187b9  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x1800187c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187c7  mov     rcx, [rcx+10h]
0x1800187cb  call    WPP_SF_s
0x1800187d0  mov     ebx, 80070216h
0x1800187d5  mov     [rsp+78h+var_44], ebx
0x1800187d9  jmp     loc_180018AFA
0x1800187de  mov     rcx, rax
0x1800187e1  shl     rcx, 4; cb
0x1800187e5  call    cs:__imp_CoTaskMemAlloc
0x1800187eb  mov     r14, rax
0x1800187ee  mov     [rsp+78h+var_38], rax
0x1800187f3  test    rax, rax
0x1800187f6  jnz     short loc_180018850
0x1800187f8  lea     rsi, WPP_GLOBAL_Control
0x1800187ff  mov     rax, cs:WPP_GLOBAL_Control
0x180018806  cmp     rax, rsi
0x180018809  jz      short loc_180018849
0x18001880b  cmp     byte ptr [rax+19h], 2
0x18001880f  jb      short loc_180018849
0x180018811  mov     edi, 100h
0x180018816  test    [rax+1Ch], edi
0x180018819  jz      short loc_180018849
0x18001881b  lea     rcx, aUnableToAlloca_0; "Unable to allocate memory for attribute"...
0x180018822  call    WppDbgPrint
0x180018827  lea     edx, [r14+31h]
0x18001882b  lea     r9, aNpsrad; "NPSRAD"
0x180018832  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180018839  mov     rcx, cs:WPP_GLOBAL_Control
0x180018840  mov     rcx, [rcx+10h]
0x180018844  call    WPP_SF_s
0x180018849  mov     ebx, 8007000Eh
0x18001884e  jmp     short loc_1800187D5
0x180018850  mov     rax, [r12]
0x180018854  lea     rcx, qword_180041518
0x18001885b  mov     [rsp+78h+var_58], rcx
0x180018860  mov     r9d, 7
0x180018866  mov     r8, r14
0x180018869  lea     rdx, [rsp+78h+arg_0]
0x180018871  mov     rcx, r12
0x180018874  mov     rax, [rax+38h]
0x180018878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001887d  mov     ebx, eax
0x18001887f  mov     [rsp+78h+var_44], eax
0x180018883  test    eax, eax
0x180018885  jns     short loc_1800188CC
0x180018887  lea     rsi, WPP_GLOBAL_Control
0x18001888e  mov     rax, cs:WPP_GLOBAL_Control
0x180018895  cmp     rax, rsi
0x180018898  jz      loc_180018AFA
0x18001889e  cmp     byte ptr [rax+19h], 2
0x1800188a2  jb      loc_180018AFA
0x1800188a8  mov     edi, 100h
0x1800188ad  test    [rax+1Ch], edi
0x1800188b0  jz      loc_180018AFA
0x1800188b6  lea     rcx, aUnableToObtain_8; "Unable to obtain information about attr"...
0x1800188bd  call    WppDbgPrint
0x1800188c2  mov     edx, 32h ; '2'
0x1800188c7  jmp     loc_180018745
0x1800188cc  mov     eax, [rsp+78h+arg_0]
0x1800188d3  test    eax, eax
0x1800188d5  jz      loc_180018AFA
0x1800188db  mov     [rsp+78h+var_48], eax
0x1800188df  xor     r15d, r15d
0x1800188e2  lea     rsi, WPP_GLOBAL_Control
0x1800188e9  mov     edi, 100h
0x1800188ee  mov     [rsp+78h+var_40], r15d
0x1800188f3  cmp     r15d, [rsp+78h+arg_0]
0x1800188fb  jnb     loc_180018AF5
0x180018901  mov     eax, r15d
0x180018904  shl     rax, 4
0x180018908  lea     r13, [rax+r14]
0x18001890c  mov     [rsp+78h+arg_10], r13
0x180018914  mov     rdx, [r13+8]
0x180018918  test    byte ptr [rdx+4], 7
0x18001891c  jz      loc_180018AEB
0x180018922  mov     edx, [rdx+8]
0x180018925  lea     eax, [rdx-1FD1h]
0x18001892b  cmp     eax, 1
0x18001892e  jbe     short loc_180018940
0x180018930  cmp     edx, 1045h
0x180018936  jz      short loc_180018940
0x180018938  cmp     edx, 1FD6h
0x18001893e  jnz     short loc_180018991
0x180018940  mov     rax, cs:WPP_GLOBAL_Control
0x180018947  cmp     rax, rsi
0x18001894a  jz      short loc_180018991
0x18001894c  cmp     byte ptr [rax+19h], 2
0x180018950  jb      short loc_180018991
0x180018952  test    [rax+1Ch], edi
0x180018955  jz      short loc_180018991
0x180018957  lea     rcx, aTheAttributeWi; "The attribute with id: '%d' should no a"...
0x18001895e  call    WppDbgPrint
0x180018963  mov     rax, [r13+8]
0x180018967  mov     edx, 33h ; '3'
0x18001896c  mov     eax, [rax+8]
0x18001896f  mov     dword ptr [rsp+78h+var_58], eax
0x180018973  lea     r9, aNpsrad; "NPSRAD"
0x18001897a  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180018981  mov     rcx, cs:WPP_GLOBAL_Control
0x180018988  mov     rcx, [rcx+10h]
0x18001898c  call    WPP_SF_sd
0x180018991  mov     r8, [r13+8]
0x180018995  mov     r13d, [r8+10h]
0x180018999  cmp     r13d, 5
0x18001899d  jnz     loc_180018A38
0x1800189a3  mov     rcx, r8
0x1800189a6  call    IASAttributeAnsiAlloc
0x1800189ab  test    eax, eax
0x1800189ad  jz      short loc_180018A19
0x1800189af  jg      short loc_1800189B5
0x1800189b1  mov     ebx, eax
0x1800189b3  jmp     short loc_1800189BE
0x1800189b5  movzx   ebx, ax
0x1800189b8  or      ebx, 80070000h
0x1800189be  mov     [rsp+78h+var_44], ebx
0x1800189c2  mov     rax, cs:WPP_GLOBAL_Control
0x1800189c9  cmp     rax, rsi
0x1800189cc  jz      loc_180018AF5
0x1800189d2  cmp     byte ptr [rax+19h], 2
0x1800189d6  jb      loc_180018AF5
0x1800189dc  test    [rax+1Ch], edi
0x1800189df  jz      loc_180018AF5
0x1800189e5  lea     rcx, aUnableToAlloca_5; "Unable to allocate memory for string at"...
0x1800189ec  call    WppDbgPrint
0x1800189f1  mov     edx, 34h ; '4'
0x1800189f6  lea     r9, aNpsrad; "NPSRAD"
0x1800189fd  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180018a04  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a0b  mov     rcx, [rcx+10h]
0x180018a0f  call    WPP_SF_s
0x180018a14  jmp     loc_180018AF5
0x180018a19  mov     rax, [rsp+78h+arg_10]
0x180018a21  mov     r8, [rax+8]
0x180018a25  mov     rcx, [r8+18h]
0x180018a29  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018a2d  inc     rax
0x180018a30  cmp     byte ptr [rcx+rax], 0
0x180018a34  jnz     short loc_180018A2D
0x180018a36  jmp     short loc_180018A46
0x180018a38  cmp     r13d, 6
0x180018a3c  jnz     loc_180018AF3
0x180018a42  mov     eax, [r8+18h]
0x180018a46  mov     ecx, 0F7h
0x180018a4b  lea     edx, [rcx+6]
0x180018a4e  cmp     dword ptr [r8+8], 0FFh
0x180018a56  cmovbe  ecx, edx
0x180018a59  cmp     eax, ecx
0x180018a5b  jbe     loc_180018AF3
0x180018a61  mov     [rsp+78h+var_50], ecx
0x180018a65  mov     dword ptr [rsp+78h+var_58], eax
0x180018a69  mov     r9d, r13d
0x180018a6c  mov     rdx, r12
0x180018a6f  call    ?SplitAndAdd@CRecvFromPipe@@AEAAJPEAUIAttributesRaw@@PEAU_IASATTRIBUTE@@W4IASTYPEENUM@@KK@Z; CRecvFromPipe::SplitAndAdd(IAttributesRaw *,_IASATTRIBUTE *,IASTYPEENUM,ulong,ulong)
0x180018a74  mov     ebx, eax
0x180018a76  mov     [rsp+78h+var_44], eax
0x180018a7a  test    eax, eax
0x180018a7c  js      short loc_180018AEB
0x180018a7e  mov     rax, [r12]
0x180018a82  mov     r8, [rsp+78h+arg_10]
0x180018a8a  mov     edx, 1
0x180018a8f  mov     rcx, r12
0x180018a92  mov     rax, [rax+20h]
0x180018a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a9b  mov     ebx, eax
0x180018a9d  mov     [rsp+78h+var_44], eax
0x180018aa1  test    eax, eax
0x180018aa3  jns     short loc_180018AEB
0x180018aa5  mov     rax, cs:WPP_GLOBAL_Control
0x180018aac  cmp     rax, rsi
0x180018aaf  jz      short loc_180018AEB
0x180018ab1  cmp     byte ptr [rax+19h], 2
0x180018ab5  jb      short loc_180018AEB
0x180018ab7  test    [rax+1Ch], edi
0x180018aba  jz      short loc_180018AEB
0x180018abc  lea     rcx, aUnableToRemove; "Unable to remove attribute from collect"...
0x180018ac3  call    WppDbgPrint
0x180018ac8  mov     edx, 35h ; '5'
0x180018acd  lea     r9, aNpsrad; "NPSRAD"
0x180018ad4  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180018adb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ae2  mov     rcx, [rcx+10h]
0x180018ae6  call    WPP_SF_s
0x180018aeb  inc     r15d
0x180018aee  jmp     loc_1800188EE
0x180018af3  jmp     short loc_180018AEB
0x180018af5  mov     r13d, [rsp+78h+var_48]
0x180018afa  test    r14, r14
0x180018afd  jz      short loc_180018B25
0x180018aff  xor     edi, edi
0x180018b01  test    r13d, r13d
0x180018b04  jz      short loc_180018B1C
0x180018b06  mov     ecx, edi
0x180018b08  add     rcx, rcx
0x180018b0b  mov     rcx, [r14+rcx*8+8]; pv
0x180018b10  call    IASAttributeRelease
0x180018b15  inc     edi
0x180018b17  cmp     edi, r13d
0x180018b1a  jb      short loc_180018B06
0x180018b1c  mov     rcx, r14; pv
0x180018b1f  call    cs:__imp_CoTaskMemFree
0x180018b25  mov     eax, ebx
0x180018b27  lea     r11, [rsp+78h+var_28]
0x180018b2c  mov     rbx, [r11+38h]
0x180018b30  mov     rsi, [r11+48h]
0x180018b34  mov     rsp, r11
0x180018b37  pop     r15
0x180018b39  pop     r14
0x180018b3b  pop     r13
0x180018b3d  pop     r12
0x180018b3f  pop     rdi
0x180018b40  retn
0x18002ef71  push    rbx
0x18002ef73  push    rbp
0x18002ef74  push    rsi
0x18002ef75  push    rdi
0x18002ef76  sub     rsp, 38h
0x18002ef7a  mov     rbp, rdx
0x18002ef7d  mov     rdi, [rbp+40h]
0x18002ef81  test    rdi, rdi
0x18002ef84  jz      short loc_18002EFAE
0x18002ef86  xor     ebx, ebx
0x18002ef88  mov     esi, [rbp+30h]
0x18002ef8b  test    esi, esi
0x18002ef8d  jz      short loc_18002EFA4
0x18002ef8f  mov     ecx, ebx
0x18002ef91  add     rcx, rcx
0x18002ef94  mov     rcx, [rdi+rcx*8+8]; pv
0x18002ef99  call    IASAttributeRelease
0x18002ef9e  inc     ebx
0x18002efa0  cmp     ebx, esi
0x18002efa2  jb      short loc_18002EF8F
0x18002efa4  mov     rcx, rdi; pv
0x18002efa7  call    cs:__imp_CoTaskMemFree
0x18002efad  nop
0x18002efae  add     rsp, 38h
0x18002efb2  pop     rdi
0x18002efb3  pop     rsi
0x18002efb4  pop     rbp
  ... truncated ...
```
