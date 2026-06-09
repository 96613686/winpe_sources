# WriteBitmaskRecord

- ea: `0x180011840`
- end: `0x180011ad5`
- name: `WriteBitmaskRecord`
- size: `661`
- prototype: `__int64 __fastcall(void *pvData, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callees

- `0x18000f144`
- `0x1800115a8`
- `0x180011618`
- `0x180011840`

## import_xrefs

- `ESENT!JetUpdate` at `0x1800119fd`
- `ESENT!JetUpdate` at `0x1800119fd`
- `ESENT!JetPrepareUpdate` at `0x1800118c8`
- `ESENT!JetPrepareUpdate` at `0x180011a31`
- `ESENT!JetPrepareUpdate` at `0x180011a5f`
- `ESENT!JetPrepareUpdate` at `0x1800118c8`
- `ESENT!JetPrepareUpdate` at `0x180011a31`
- `ESENT!JetPrepareUpdate` at `0x180011a5f`
- `ESENT!JetSetColumn` at `0x18001190f`
- `ESENT!JetSetColumn` at `0x180011967`
- `ESENT!JetSetColumn` at `0x1800119a1`
- `ESENT!JetSetColumn` at `0x1800119d7`
- `ESENT!JetSetColumn` at `0x18001190f`
- `ESENT!JetSetColumn` at `0x180011967`
- `ESENT!JetSetColumn` at `0x1800119a1`
- `ESENT!JetSetColumn` at `0x1800119d7`

## string_xrefs

- `0x1800118d6`: `Flushbitmask:JetPrepareUpdate`
- `0x180011a0b`: `Bitmask : JetUpdate`
- `0x180011a3f`: `Bitmask : JetUpdate`

## pseudocode

```c
__int64 __fastcall WriteBitmaskRecord(_DWORD *pvData, char *a2)
{
  int v2; // eax
  JET_SESID v5; // rsi
  unsigned int v6; // eax
  __int64 result; // rax
  unsigned int v8; // eax
  const void *v9; // r9
  int v10; // eax
  unsigned int cbData; // ecx
  _DWORD *v12; // r15
  __int64 v13; // r14
  unsigned int v14; // ebp
  __int64 v15; // r8
  JET_ERR v16; // eax
  __int64 v17; // rdx

  v2 = pvData[2];
  if ( !v2 )
  {
    *((_DWORD *)a2 + 1) += *pvData;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_dddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids,
      *(unsigned int *)a2,
      *((_DWORD *)a2 + 1),
      *pvData,
      v2);
  v5 = DhcpGlobalJetServerSession;
  v6 = JetPrepareUpdate(DhcpGlobalJetServerSession, BitmaskTbl, 0);
  result = DhcpMapJetError(v6, "Flushbitmask:JetPrepareUpdate");
  if ( !(_DWORD)result )
  {
    v8 = JetSetColumn(v5, BitmaskTbl, columnid, a2, 4u, 0, 0);
    if ( v8 )
      goto LABEL_18;
    v9 = (const void *)*((_QWORD *)pvData + 2);
    v10 = *pvData >> 3;
    if ( v9 )
    {
      cbData = v10 + 1;
      if ( (unsigned int)(8 * v10) >= *pvData )
        cbData = *pvData >> 3;
    }
    else
    {
      cbData = 0;
      v9 = 0;
    }
    v8 = JetSetColumn(v5, BitmaskTbl, dword_1800F6068, v9, cbData, 0, 0);
    if ( v8
      || (v12 = a2 + 4, (v8 = JetSetColumn(v5, BitmaskTbl, dword_1800F6078, a2 + 4, 4u, 0, 0)) != 0)
      || (v8 = JetSetColumn(v5, BitmaskTbl, dword_1800F6088, pvData, 4u, 0, 0)) != 0 )
    {
LABEL_18:
      v14 = DhcpMapJetError(v8, "Bitmask : JetUpdate");
      v16 = JetPrepareUpdate(v5, BitmaskTbl, 3u);
      v12 = a2 + 4;
    }
    else
    {
      v13 = (unsigned int)JetUpdate(v5, BitmaskTbl, 0, 0, 0);
      v14 = DhcpMapJetError(v13, "Bitmask : JetUpdate");
      if ( !(_DWORD)v13 )
      {
LABEL_20:
        if ( v14 )
          return v14;
        v17 = (unsigned int)(*v12 + *pvData);
        *v12 = v17;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        {
          WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v15, *(unsigned int *)a2, v17, *pvData, v13);
        }
        return 0;
      }
      v16 = JetPrepareUpdate(v5, BitmaskTbl, 3u);
    }
    LODWORD(v13) = v16;
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x180011840  mov     [rsp+arg_0], rbx
0x180011845  mov     [rsp+arg_8], rbp
0x18001184a  mov     [rsp+arg_10], rsi
0x18001184f  push    rdi
0x180011850  push    r14
0x180011852  push    r15
0x180011854  sub     rsp, 40h
0x180011858  mov     eax, [rcx+8]
0x18001185b  mov     rdi, rdx
0x18001185e  mov     rbx, rcx
0x180011861  test    eax, eax
0x180011863  jnz     short loc_18001186F
0x180011865  mov     eax, [rcx]
0x180011867  add     [rdx+4], eax
0x18001186a  jmp     loc_180011AB9
0x18001186f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011876  lea     rdx, WPP_GLOBAL_Control
0x18001187d  cmp     rcx, rdx
0x180011880  jz      short loc_1800118B4
0x180011882  test    dword ptr [rcx+1Ch], 10000000h
0x180011889  jz      short loc_1800118B4
0x18001188b  mov     r9d, [rdi]
0x18001188e  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x180011895  mov     rcx, [rcx+10h]
0x180011899  mov     edx, 6Bh ; 'k'
0x18001189e  mov     dword ptr [rsp+58h+psetinfo], eax; psetinfo
0x1800118a2  mov     eax, [rbx]
0x1800118a4  mov     [rsp+58h+grbit], eax; grbit
0x1800118a8  mov     eax, [rdi+4]
0x1800118ab  mov     [rsp+58h+cbData], eax
0x1800118af  call    WPP_SF_dddd
0x1800118b4  mov     rsi, cs:DhcpGlobalJetServerSession
0x1800118bb  xor     r8d, r8d; prep
0x1800118be  mov     rdx, cs:BitmaskTbl; tableid
0x1800118c5  mov     rcx, rsi; sesid
0x1800118c8  call    cs:__imp_JetPrepareUpdate
0x1800118cf  nop     dword ptr [rax+rax+00h]
0x1800118d4  mov     ecx, eax
0x1800118d6  lea     rdx, aFlushbitmaskJe; "Flushbitmask:JetPrepareUpdate"
0x1800118dd  call    DhcpMapJetError
0x1800118e2  test    eax, eax
0x1800118e4  jnz     loc_180011ABB
0x1800118ea  and     [rsp+58h+psetinfo], 0
0x1800118f0  lea     ebp, [rax+4]
0x1800118f3  and     [rsp+58h+grbit], eax
0x1800118f7  mov     r9, rdi; pvData
0x1800118fa  mov     r8d, cs:columnid; columnid
0x180011901  mov     rcx, rsi; sesid
0x180011904  mov     rdx, cs:BitmaskTbl; tableid
0x18001190b  mov     [rsp+58h+cbData], ebp; cbData
0x18001190f  call    cs:__imp_JetSetColumn
0x180011916  nop     dword ptr [rax+rax+00h]
0x18001191b  test    eax, eax
0x18001191d  jnz     loc_180011A3F
0x180011923  mov     eax, [rbx]
0x180011925  mov     r9, [rbx+10h]
0x180011929  shr     eax, 3
0x18001192c  lea     edx, ds:0[rax*8]
0x180011933  test    r9, r9
0x180011936  jz      short loc_180011942
0x180011938  cmp     edx, [rbx]
0x18001193a  lea     ecx, [rax+1]
0x18001193d  cmovnb  ecx, eax
0x180011940  jmp     short loc_180011947
0x180011942  xor     ecx, ecx
0x180011944  xor     r9d, r9d; pvData
0x180011947  and     [rsp+58h+psetinfo], 0
0x18001194d  and     [rsp+58h+grbit], 0
0x180011952  mov     r8d, cs:dword_1800F6068; columnid
0x180011959  mov     rdx, cs:BitmaskTbl; tableid
0x180011960  mov     [rsp+58h+cbData], ecx; cbData
0x180011964  mov     rcx, rsi; sesid
0x180011967  call    cs:__imp_JetSetColumn
0x18001196e  nop     dword ptr [rax+rax+00h]
0x180011973  test    eax, eax
0x180011975  jnz     loc_180011A3F
0x18001197b  and     [rsp+58h+psetinfo], 0
0x180011981  lea     r15, [rdi+4]
0x180011985  and     [rsp+58h+grbit], eax
0x180011989  mov     r9, r15; pvData
0x18001198c  mov     r8d, cs:dword_1800F6078; columnid
0x180011993  mov     rcx, rsi; sesid
0x180011996  mov     rdx, cs:BitmaskTbl; tableid
0x18001199d  mov     [rsp+58h+cbData], ebp; cbData
0x1800119a1  call    cs:__imp_JetSetColumn
0x1800119a8  nop     dword ptr [rax+rax+00h]
0x1800119ad  test    eax, eax
0x1800119af  jnz     loc_180011A3F
0x1800119b5  and     [rsp+58h+psetinfo], 0
0x1800119bb  mov     r9, rbx; pvData
0x1800119be  and     [rsp+58h+grbit], eax
0x1800119c2  mov     rcx, rsi; sesid
0x1800119c5  mov     r8d, cs:dword_1800F6088; columnid
0x1800119cc  mov     rdx, cs:BitmaskTbl; tableid
0x1800119d3  mov     [rsp+58h+cbData], ebp; pcbActual
0x1800119d7  call    cs:__imp_JetSetColumn
0x1800119de  nop     dword ptr [rax+rax+00h]
0x1800119e3  test    eax, eax
0x1800119e5  jnz     short loc_180011A3F
0x1800119e7  mov     rdx, cs:BitmaskTbl; tableid
0x1800119ee  xor     r9d, r9d; cbBookmark
0x1800119f1  and     qword ptr [rsp+58h+cbData], 0
0x1800119f7  xor     r8d, r8d; pvBookmark
0x1800119fa  mov     rcx, rsi; sesid
0x1800119fd  call    cs:__imp_JetUpdate
0x180011a04  nop     dword ptr [rax+rax+00h]
0x180011a09  mov     ecx, eax
0x180011a0b  lea     rdx, aBitmaskJetupda; "Bitmask : JetUpdate"
0x180011a12  mov     r14d, eax
0x180011a15  call    DhcpMapJetError
0x180011a1a  mov     ebp, eax
0x180011a1c  test    r14d, r14d
0x180011a1f  jz      short loc_180011A72
0x180011a21  mov     rdx, cs:BitmaskTbl; tableid
0x180011a28  mov     r8d, 3; prep
0x180011a2e  mov     rcx, rsi; sesid
0x180011a31  call    cs:__imp_JetPrepareUpdate
0x180011a38  nop     dword ptr [rax+rax+00h]
0x180011a3d  jmp     short loc_180011A6F
0x180011a3f  lea     rdx, aBitmaskJetupda; "Bitmask : JetUpdate"
0x180011a46  mov     ecx, eax
0x180011a48  call    DhcpMapJetError
0x180011a4d  mov     rdx, cs:BitmaskTbl; tableid
0x180011a54  mov     r8d, 3; prep
0x180011a5a  mov     rcx, rsi; sesid
0x180011a5d  mov     ebp, eax
0x180011a5f  call    cs:__imp_JetPrepareUpdate
0x180011a66  nop     dword ptr [rax+rax+00h]
0x180011a6b  lea     r15, [rdi+4]
0x180011a6f  mov     r14d, eax
0x180011a72  test    ebp, ebp
0x180011a74  jz      short loc_180011A7A
0x180011a76  mov     eax, ebp
0x180011a78  jmp     short loc_180011ABB
0x180011a7a  mov     edx, [rbx]
0x180011a7c  add     edx, [r15]
0x180011a7f  mov     [r15], edx
0x180011a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a89  lea     rax, WPP_GLOBAL_Control
0x180011a90  cmp     rcx, rax
0x180011a93  jz      short loc_180011AB9
0x180011a95  test    dword ptr [rcx+1Ch], 10000000h
0x180011a9c  jz      short loc_180011AB9
0x180011a9e  mov     eax, [rbx]
0x180011aa0  mov     r9d, [rdi]
0x180011aa3  mov     rcx, [rcx+10h]
0x180011aa7  mov     dword ptr [rsp+58h+psetinfo], r14d
0x180011aac  mov     [rsp+58h+grbit], eax
0x180011ab0  mov     [rsp+58h+cbData], edx
0x180011ab4  call    WPP_SF_DDDd
0x180011ab9  xor     eax, eax
0x180011abb  mov     rbx, [rsp+58h+arg_0]
0x180011ac0  mov     rbp, [rsp+58h+arg_8]
0x180011ac5  mov     rsi, [rsp+58h+arg_10]
0x180011aca  add     rsp, 40h
0x180011ace  pop     r15
0x180011ad0  pop     r14
0x180011ad2  pop     rdi
0x180011ad3  retn
```
