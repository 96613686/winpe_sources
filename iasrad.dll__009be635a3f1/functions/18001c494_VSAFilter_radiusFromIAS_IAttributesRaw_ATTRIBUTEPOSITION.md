# VSAFilter::radiusFromIAS(IAttributesRaw *,_ATTRIBUTEPOSITION &)

- ea: `0x18001c494`
- end: `0x18001c7dc`
- name: `?radiusFromIAS@VSAFilter@@IEBAXPEAUIAttributesRaw@@AEAU_ATTRIBUTEPOSITION@@@Z`
- size: `840`
- prototype: `void(VSAFilter *__hidden this, struct IAttributesRaw *, struct _ATTRIBUTEPOSITION *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c7f0`

## callees

- `0x18000dc54`
- `0x180014478`
- `0x18001b0ec`
- `0x18001b2c8`
- `0x18001b3f0`
- `0x18001c494`
- `0x18001d124`
- `0x18001d31c`
- `0x18002acfc`
- `0x18002c564`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c5a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c5a9`

## string_xrefs

- `0x18001c717`: `Error when converting IAS attribute to RADIUS VSA: arithmetic overflow during attr length computation (id %d)`
- `0x18001c75b`: `Error when converting IAS attribute to RADIUS VSA: arithmetic overflow during attr length computation (id %d)`
- `0x18001c797`: `Error when converting IAS attribute to RADIUS VSA: arithmetic overflow during attr length computation (id %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VSAFilter::radiusFromIAS(VSAFilter *this, struct IAttributesRaw *a2, struct _ATTRIBUTEPOSITION *a3)
{
  unsigned int *v5; // r11
  __int64 v6; // r10
  __int64 *i; // r8
  int *v8; // rdi
  unsigned int EncodedSize; // eax
  unsigned int v10; // ebp
  unsigned int v11; // r8d
  unsigned int v12; // edx
  unsigned int v13; // esi
  _BYTE *v14; // rdx
  VSAFilter *v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  RadiusUtil *v18; // rax
  const struct _IASATTRIBUTE *v19; // r8
  int v20; // eax
  int v21; // edx
  VSAFilter *v22; // [rsp+50h] [rbp+8h] BYREF

  v22 = this;
  v5 = (unsigned int *)*((_QWORD *)a3 + 1);
  v6 = v5[2];
  for ( i = *(__int64 **)(*(_QWORD *)(VSAFilter::theDictionary + 24LL)
                        + 8 * (v6 & *(_QWORD *)(VSAFilter::theDictionary + 8LL))); ; i = (__int64 *)*i )
  {
    if ( !i )
      return;
    v8 = (int *)(i + 1);
    if ( *((_DWORD *)i + 6) == (_DWORD)v6 )
      break;
  }
  if ( i != (__int64 *)-8LL )
  {
    EncodedSize = RadiusUtil::getEncodedSize((RadiusUtil *)v5, a2);
    v10 = EncodedSize;
    v11 = v8[2] + 4;
    if ( (unsigned int)v8[2] >= 0xFFFFFFFC )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Error when converting IAS attribute to RADIUS VSA: arithmetic overflow during attr length computation (id %d)");
        v21 = 11;
        goto LABEL_37;
      }
    }
    else
    {
      v12 = v11 + v8[3];
      if ( v12 < v11 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Error when converting IAS attribute to RADIUS VSA: arithmetic overflow during attr length computation (id %d)");
          v21 = 12;
          goto LABEL_37;
        }
      }
      else
      {
        v13 = v12 + EncodedSize;
        if ( v12 + EncodedSize >= v12 )
        {
          if ( v13 > 0xFD )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WppDbgPrint("Error when converting IAS attribute to RADIUS VSA: attr larger than 253 bytes (id %d)");
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                (unsigned int)WPP_d362265ad4cf301a2e1f0d44d2a81ab5_Traceguids,
                (unsigned int)"NPSRAD",
                *(_DWORD *)(*((_QWORD *)a3 + 1) + 8LL));
            }
            _com_issue_error(-2147024809);
          }
          IASTL::IASAttribute::_alloc((IASTL::IASAttribute *)&v22);
          v14 = CoTaskMemAlloc(v13);
          if ( !v14 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WppDbgPrint("Error when converting IAS attribute to RADIUS VSA: not enough memory for attr value (id %d)");
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                (unsigned int)WPP_d362265ad4cf301a2e1f0d44d2a81ab5_Traceguids,
                (unsigned int)"NPSRAD",
                *(_DWORD *)(*((_QWORD *)a3 + 1) + 8LL));
            }
            _com_issue_error(-2147024882);
          }
          v15 = v22;
          *((_DWORD *)v22 + 1) = *(_DWORD *)(*((_QWORD *)a3 + 1) + 4LL);
          *((_DWORD *)v15 + 2) = 26;
          *((_DWORD *)v15 + 4) = 6;
          *((_DWORD *)v15 + 6) = v13;
          *((_QWORD *)v15 + 4) = v14;
          v16 = *v8;
          *v14 = HIBYTE(*v8);
          v14[1] = BYTE2(v16);
          v14[2] = BYTE1(v16);
          v14[3] = v16;
          v17 = IASInsertField(v14 + 4, (unsigned int)v8[2], (unsigned int)v8[1]);
          v18 = (RadiusUtil *)IASInsertField(v17, (unsigned int)v8[3], v8[2] + v8[3] + v10);
          RadiusUtil::encode(v18, *((unsigned __int8 **)a3 + 1), v19);
          v20 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, __int64, struct _ATTRIBUTEPOSITION *))(*(_QWORD *)a2 + 32LL))(
                  a2,
                  1,
                  a3);
          if ( v20 < 0 )
            _com_issue_error(v20);
          IASTL::IASAttribute::store((IASTL::IASAttribute *)&v22, a2);
          IASTL::IASAttribute::_release((IASTL::IASAttribute *)&v22);
          return;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Error when converting IAS attribute to RADIUS VSA: arithmetic overflow during attr length computation (id %d)");
          v21 = 13;
LABEL_37:
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            (unsigned int)WPP_d362265ad4cf301a2e1f0d44d2a81ab5_Traceguids,
            (unsigned int)"NPSRAD",
            *(_DWORD *)(*((_QWORD *)a3 + 1) + 8LL));
        }
      }
    }
    _com_issue_error(-2147024362);
  }
}

```

## disassembly

```asm
0x18001c494  mov     [rsp+arg_8], rbx
0x18001c499  mov     [rsp+arg_10], rbp
0x18001c49e  mov     [rsp+arg_0], rcx
0x18001c4a3  push    rsi
0x18001c4a4  push    rdi
0x18001c4a5  push    r14
0x18001c4a7  sub     rsp, 30h
0x18001c4ab  mov     rbx, r8
0x18001c4ae  mov     r14, rdx
0x18001c4b1  mov     r11, [r8+8]
0x18001c4b5  mov     r10d, [r11+8]
0x18001c4b9  mov     r9, cs:?theDictionary@VSAFilter@@1VVSADictionary@@A; VSADictionary VSAFilter::theDictionary
0x18001c4c0  mov     rcx, [r9+8]
0x18001c4c4  and     rcx, r10
0x18001c4c7  mov     rax, [r9+18h]
0x18001c4cb  mov     r8, [rax+rcx*8]
0x18001c4cf  test    r8, r8
0x18001c4d2  jz      loc_18001C6CF
0x18001c4d8  lea     rdi, [r8+8]
0x18001c4dc  cmp     [rdi+10h], r10d
0x18001c4e0  jz      short loc_18001C4E7
0x18001c4e2  mov     r8, [r8]
0x18001c4e5  jmp     short loc_18001C4CF
0x18001c4e7  test    rdi, rdi
0x18001c4ea  jz      loc_18001C6CF
0x18001c4f0  mov     rcx, r11; this
0x18001c4f3  call    ?getEncodedSize@RadiusUtil@@YAKAEBU_IASATTRIBUTE@@@Z; RadiusUtil::getEncodedSize(_IASATTRIBUTE const &)
0x18001c4f8  mov     ebp, eax
0x18001c4fa  mov     r8d, [rdi+8]
0x18001c4fe  add     r8d, 4
0x18001c502  cmp     r8d, 4
0x18001c506  jb      loc_18001C76E
0x18001c50c  mov     edx, [rdi+0Ch]
0x18001c50f  add     edx, r8d
0x18001c512  cmp     edx, r8d
0x18001c515  jb      loc_18001C72A
0x18001c51b  lea     esi, [rdx+rax]
0x18001c51e  cmp     esi, edx
0x18001c520  jb      loc_18001C6E2
0x18001c526  cmp     esi, 0FDh
0x18001c52c  jbe     short loc_18001C59C
0x18001c52e  lea     rax, WPP_GLOBAL_Control
0x18001c535  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c53c  cmp     rcx, rax
0x18001c53f  jz      short loc_18001C591
0x18001c541  cmp     byte ptr [rcx+19h], 2
0x18001c545  jb      short loc_18001C591
0x18001c547  test    dword ptr [rcx+1Ch], 100h
0x18001c54e  jz      short loc_18001C591
0x18001c550  mov     rdx, [rbx+8]
0x18001c554  mov     edx, [rdx+8]
0x18001c557  lea     rcx, aErrorWhenConve_1; "Error when converting IAS attribute to "...
0x18001c55e  call    WppDbgPrint
0x18001c563  mov     rax, [rbx+8]
0x18001c567  mov     edx, 0Eh
0x18001c56c  mov     eax, [rax+8]
0x18001c56f  mov     [rsp+48h+var_28], eax
0x18001c573  lea     r9, aNpsrad; "NPSRAD"
0x18001c57a  lea     r8, WPP_d362265ad4cf301a2e1f0d44d2a81ab5_Traceguids
0x18001c581  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c588  mov     rcx, [rcx+10h]
0x18001c58c  call    WPP_SF_sd
0x18001c591  mov     ecx, 80070057h; int
0x18001c596  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001c59c  lea     rcx, [rsp+48h+arg_0]; this
0x18001c5a1  call    ?_alloc@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::_alloc(void)
0x18001c5a6  nop
0x18001c5a7  mov     ecx, esi; cb
0x18001c5a9  call    cs:__imp_CoTaskMemAlloc
0x18001c5af  mov     rdx, rax
0x18001c5b2  test    rax, rax
0x18001c5b5  jnz     short loc_18001C625
0x18001c5b7  lea     rax, WPP_GLOBAL_Control
0x18001c5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5c5  cmp     rcx, rax
0x18001c5c8  jz      short loc_18001C61A
0x18001c5ca  cmp     byte ptr [rcx+19h], 2
0x18001c5ce  jb      short loc_18001C61A
0x18001c5d0  test    dword ptr [rcx+1Ch], 100h
0x18001c5d7  jz      short loc_18001C61A
0x18001c5d9  mov     rdx, [rbx+8]
0x18001c5dd  mov     edx, [rdx+8]
0x18001c5e0  lea     rcx, aErrorWhenConve; "Error when converting IAS attribute to "...
0x18001c5e7  call    WppDbgPrint
0x18001c5ec  mov     rax, [rbx+8]
0x18001c5f0  mov     edx, 0Fh
0x18001c5f5  mov     eax, [rax+8]
0x18001c5f8  mov     [rsp+48h+var_28], eax
0x18001c5fc  lea     r9, aNpsrad; "NPSRAD"
0x18001c603  lea     r8, WPP_d362265ad4cf301a2e1f0d44d2a81ab5_Traceguids
0x18001c60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c611  mov     rcx, [rcx+10h]
0x18001c615  call    WPP_SF_sd
0x18001c61a  mov     ecx, 8007000Eh; int
0x18001c61f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001c625  mov     rax, [rbx+8]
0x18001c629  mov     ecx, [rax+4]
0x18001c62c  mov     rax, [rsp+48h+arg_0]
0x18001c631  mov     [rax+4], ecx
0x18001c634  mov     dword ptr [rax+8], 1Ah
0x18001c63b  mov     dword ptr [rax+10h], 6
0x18001c642  mov     [rax+18h], esi
0x18001c645  mov     [rax+20h], rdx
0x18001c649  mov     ecx, [rdi]
0x18001c64b  mov     eax, ecx
0x18001c64d  shr     eax, 18h
0x18001c650  mov     [rdx], al
0x18001c652  mov     eax, ecx
0x18001c654  shr     eax, 10h
0x18001c657  mov     [rdx+1], al
0x18001c65a  mov     eax, ecx
0x18001c65c  shr     eax, 8
0x18001c65f  mov     [rdx+2], al
0x18001c662  mov     [rdx+3], cl
0x18001c665  lea     rcx, [rdx+4]
0x18001c669  mov     r8d, [rdi+4]
0x18001c66d  mov     edx, [rdi+8]
0x18001c670  call    IASInsertField
0x18001c675  mov     edx, [rdi+0Ch]
0x18001c678  lea     r8d, [rdx+rbp]
0x18001c67c  add     r8d, [rdi+8]
0x18001c680  mov     rcx, rax
0x18001c683  call    IASInsertField
0x18001c688  mov     rdx, [rbx+8]; unsigned __int8 *
0x18001c68c  mov     rcx, rax; this
0x18001c68f  call    ?encode@RadiusUtil@@YAXPEAEAEBU_IASATTRIBUTE@@@Z; RadiusUtil::encode(uchar *,_IASATTRIBUTE const &)
0x18001c694  mov     rax, [r14]
0x18001c697  mov     r8, rbx
0x18001c69a  mov     edx, 1
0x18001c69f  mov     rcx, r14
0x18001c6a2  mov     rax, [rax+20h]
0x18001c6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6ab  test    eax, eax
0x18001c6ad  jns     short loc_18001C6B7
0x18001c6af  mov     ecx, eax; int
0x18001c6b1  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001c6b7  mov     rdx, r14; struct IAttributesRaw *
0x18001c6ba  lea     rcx, [rsp+48h+arg_0]; this
0x18001c6bf  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x18001c6c4  nop
0x18001c6c5  lea     rcx, [rsp+48h+arg_0]; this
0x18001c6ca  call    ?_release@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::_release(void)
0x18001c6cf  mov     rbx, [rsp+48h+arg_8]
0x18001c6d4  mov     rbp, [rsp+48h+arg_10]
0x18001c6d9  add     rsp, 30h
0x18001c6dd  pop     r14
0x18001c6df  pop     rdi
0x18001c6e0  pop     rsi
0x18001c6e1  retn
0x18001c6e2  lea     rax, WPP_GLOBAL_Control
0x18001c6e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6f0  cmp     rcx, rax
0x18001c6f3  jz      loc_18001C7D1
0x18001c6f9  cmp     byte ptr [rcx+19h], 2
0x18001c6fd  jb      loc_18001C7D1
0x18001c703  test    dword ptr [rcx+1Ch], 100h
0x18001c70a  jz      loc_18001C7D1
0x18001c710  mov     rdx, [rbx+8]
0x18001c714  mov     edx, [rdx+8]
0x18001c717  lea     rcx, aErrorWhenConve_0; "Error when converting IAS attribute to "...
0x18001c71e  call    WppDbgPrint
0x18001c723  mov     edx, 0Dh
0x18001c728  jmp     short loc_18001C7A8
0x18001c72a  lea     rax, WPP_GLOBAL_Control
0x18001c731  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c738  cmp     rcx, rax
0x18001c73b  jz      loc_18001C7D1
0x18001c741  cmp     byte ptr [rcx+19h], 2
0x18001c745  jb      loc_18001C7D1
0x18001c74b  test    dword ptr [rcx+1Ch], 100h
0x18001c752  jz      short loc_18001C7D1
0x18001c754  mov     rdx, [rbx+8]
0x18001c758  mov     edx, [rdx+8]
0x18001c75b  lea     rcx, aErrorWhenConve_0; "Error when converting IAS attribute to "...
0x18001c762  call    WppDbgPrint
0x18001c767  mov     edx, 0Ch
0x18001c76c  jmp     short loc_18001C7A8
0x18001c76e  lea     rax, WPP_GLOBAL_Control
0x18001c775  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c77c  cmp     rcx, rax
0x18001c77f  jz      short loc_18001C7D1
0x18001c781  cmp     byte ptr [rcx+19h], 2
0x18001c785  jb      short loc_18001C7D1
0x18001c787  test    dword ptr [rcx+1Ch], 100h
0x18001c78e  jz      short loc_18001C7D1
0x18001c790  mov     rdx, [rbx+8]
0x18001c794  mov     edx, [rdx+8]
0x18001c797  lea     rcx, aErrorWhenConve_0; "Error when converting IAS attribute to "...
0x18001c79e  call    WppDbgPrint
0x18001c7a3  mov     edx, 0Bh
0x18001c7a8  mov     rax, [rbx+8]
0x18001c7ac  mov     eax, [rax+8]
0x18001c7af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7b6  mov     [rsp+48h+var_28], eax
0x18001c7ba  lea     r9, aNpsrad; "NPSRAD"
0x18001c7c1  lea     r8, WPP_d362265ad4cf301a2e1f0d44d2a81ab5_Traceguids
0x18001c7c8  mov     rcx, [rcx+10h]
0x18001c7cc  call    WPP_SF_sd
0x18001c7d1  mov     ecx, 80070216h; int
0x18001c7d6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
