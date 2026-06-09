# WriteBitmaskRecord

- ea: `0x180010f60`
- end: `0x180011205`
- name: `WriteBitmaskRecord`
- size: `677`
- prototype: `__int64 __fastcall(void *pvData, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callees

- `0x18000e814`
- `0x180010cbc`
- `0x180010d2c`
- `0x180010f60`

## import_xrefs

- `ESENT!JetUpdate` at `0x18001112d`
- `ESENT!JetUpdate` at `0x18001112d`
- `ESENT!JetPrepareUpdate` at `0x180010fe8`
- `ESENT!JetPrepareUpdate` at `0x180011161`
- `ESENT!JetPrepareUpdate` at `0x18001118f`
- `ESENT!JetPrepareUpdate` at `0x180010fe8`
- `ESENT!JetPrepareUpdate` at `0x180011161`
- `ESENT!JetPrepareUpdate` at `0x18001118f`
- `ESENT!JetSetColumn` at `0x180011032`
- `ESENT!JetSetColumn` at `0x18001108e`
- `ESENT!JetSetColumn` at `0x1800110cb`
- `ESENT!JetSetColumn` at `0x180011104`
- `ESENT!JetSetColumn` at `0x180011032`
- `ESENT!JetSetColumn` at `0x18001108e`
- `ESENT!JetSetColumn` at `0x1800110cb`
- `ESENT!JetSetColumn` at `0x180011104`

## string_xrefs

- `0x180010ff6`: `Flushbitmask:JetPrepareUpdate`
- `0x18001113b`: `Bitmask : JetUpdate`
- `0x18001116f`: `Bitmask : JetUpdate`

## pseudocode

```c
__int64 __fastcall WriteBitmaskRecord(unsigned int *pvData, char *a2)
{
  unsigned int v2; // eax
  JET_SESID v5; // rsi
  unsigned int v6; // eax
  __int64 result; // rax
  unsigned int v8; // eax
  const void *v9; // r9
  unsigned int cbData; // eax
  _DWORD *v11; // r15
  __int64 v12; // r14
  unsigned int v13; // ebp
  __int64 v14; // r8
  JET_ERR v15; // eax
  __int64 v16; // rdx

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
    if ( v9 )
    {
      cbData = (*pvData >> 3) + 1;
      if ( (*pvData & 0xFFFFFFF8) >= *pvData )
        cbData = *pvData >> 3;
    }
    else
    {
      cbData = 0;
      v9 = 0;
    }
    v8 = JetSetColumn(v5, BitmaskTbl, dword_1800F8068, v9, cbData, 0, 0);
    if ( v8
      || (v11 = a2 + 4, (v8 = JetSetColumn(v5, BitmaskTbl, dword_1800F8078, a2 + 4, 4u, 0, 0)) != 0)
      || (v8 = JetSetColumn(v5, BitmaskTbl, dword_1800F8088, pvData, 4u, 0, 0)) != 0 )
    {
LABEL_18:
      v13 = DhcpMapJetError(v8, "Bitmask : JetUpdate");
      v15 = JetPrepareUpdate(v5, BitmaskTbl, 3u);
      v11 = a2 + 4;
    }
    else
    {
      v12 = (unsigned int)JetUpdate(v5, BitmaskTbl, 0, 0, 0);
      v13 = DhcpMapJetError(v12, "Bitmask : JetUpdate");
      if ( !(_DWORD)v12 )
      {
LABEL_20:
        if ( v13 )
          return v13;
        v16 = *pvData + *v11;
        *v11 = v16;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        {
          WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v14, *(unsigned int *)a2, v16, *pvData, v12);
        }
        return 0;
      }
      v15 = JetPrepareUpdate(v5, BitmaskTbl, 3u);
    }
    LODWORD(v12) = v15;
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x180010f60  mov     [rsp+arg_0], rbx
0x180010f65  mov     [rsp+arg_8], rbp
0x180010f6a  mov     [rsp+arg_10], rsi
0x180010f6f  push    rdi
0x180010f70  push    r14
0x180010f72  push    r15
0x180010f74  sub     rsp, 40h
0x180010f78  mov     eax, [rcx+8]
0x180010f7b  mov     rdi, rdx
0x180010f7e  mov     rbx, rcx
0x180010f81  test    eax, eax
0x180010f83  jnz     short loc_180010F8F
0x180010f85  mov     eax, [rcx]
0x180010f87  add     [rdx+4], eax
0x180010f8a  jmp     loc_1800111E9
0x180010f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f96  lea     rdx, WPP_GLOBAL_Control
0x180010f9d  cmp     rcx, rdx
0x180010fa0  jz      short loc_180010FD4
0x180010fa2  test    dword ptr [rcx+1Ch], 10000000h
0x180010fa9  jz      short loc_180010FD4
0x180010fab  mov     r9d, [rdi]
0x180010fae  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x180010fb5  mov     rcx, [rcx+10h]
0x180010fb9  mov     edx, 6Bh ; 'k'
0x180010fbe  mov     dword ptr [rsp+58h+psetinfo], eax
0x180010fc2  mov     eax, [rbx]
0x180010fc4  mov     [rsp+58h+grbit], eax
0x180010fc8  mov     eax, [rdi+4]
0x180010fcb  mov     [rsp+58h+cbData], eax
0x180010fcf  call    WPP_SF_dddd
0x180010fd4  mov     rsi, cs:DhcpGlobalJetServerSession
0x180010fdb  xor     r8d, r8d; prep
0x180010fde  mov     rdx, cs:BitmaskTbl; tableid
0x180010fe5  mov     rcx, rsi; sesid
0x180010fe8  call    cs:__imp_JetPrepareUpdate
0x180010fef  nop     dword ptr [rax+rax+00h]
0x180010ff4  mov     ecx, eax
0x180010ff6  lea     rdx, aFlushbitmaskJe; "Flushbitmask:JetPrepareUpdate"
0x180010ffd  call    DhcpMapJetError
0x180011002  test    eax, eax
0x180011004  jnz     loc_1800111EB
0x18001100a  mov     r8d, cs:columnid; columnid
0x180011011  lea     ebp, [rax+4]
0x180011014  mov     rdx, cs:BitmaskTbl; tableid
0x18001101b  mov     r9, rdi; pvData
0x18001101e  mov     [rsp+58h+psetinfo], 0; psetinfo
0x180011027  mov     rcx, rsi; sesid
0x18001102a  mov     [rsp+58h+grbit], eax; grbit
0x18001102e  mov     [rsp+58h+cbData], ebp; cbData
0x180011032  call    cs:__imp_JetSetColumn
0x180011039  nop     dword ptr [rax+rax+00h]
0x18001103e  test    eax, eax
0x180011040  jnz     loc_18001116F
0x180011046  mov     edx, [rbx]
0x180011048  mov     ecx, [rbx]
0x18001104a  and     edx, 0FFFFFFF8h
0x18001104d  mov     r9, [rbx+10h]
0x180011051  shr     ecx, 3
0x180011054  test    r9, r9
0x180011057  jz      short loc_180011063
0x180011059  cmp     edx, [rbx]
0x18001105b  lea     eax, [rcx+1]
0x18001105e  cmovnb  eax, ecx
0x180011061  jmp     short loc_180011068
0x180011063  xor     eax, eax
0x180011065  xor     r9d, r9d; pvData
0x180011068  mov     r8d, cs:dword_1800F8068; columnid
0x18001106f  mov     rcx, rsi; sesid
0x180011072  mov     rdx, cs:BitmaskTbl; tableid
0x180011079  mov     [rsp+58h+psetinfo], 0; psetinfo
0x180011082  mov     [rsp+58h+grbit], 0; grbit
0x18001108a  mov     [rsp+58h+cbData], eax; cbData
0x18001108e  call    cs:__imp_JetSetColumn
0x180011095  nop     dword ptr [rax+rax+00h]
0x18001109a  test    eax, eax
0x18001109c  jnz     loc_18001116F
0x1800110a2  mov     r8d, cs:dword_1800F8078; columnid
0x1800110a9  lea     r15, [rdi+4]
0x1800110ad  mov     rdx, cs:BitmaskTbl; tableid
0x1800110b4  mov     r9, r15; pvData
0x1800110b7  mov     [rsp+58h+psetinfo], 0; psetinfo
0x1800110c0  mov     rcx, rsi; sesid
0x1800110c3  mov     [rsp+58h+grbit], eax; grbit
0x1800110c7  mov     [rsp+58h+cbData], ebp; cbData
0x1800110cb  call    cs:__imp_JetSetColumn
0x1800110d2  nop     dword ptr [rax+rax+00h]
0x1800110d7  test    eax, eax
0x1800110d9  jnz     loc_18001116F
0x1800110df  mov     r8d, cs:dword_1800F8088; columnid
0x1800110e6  mov     r9, rbx; pvData
0x1800110e9  mov     rdx, cs:BitmaskTbl; tableid
0x1800110f0  mov     rcx, rsi; sesid
0x1800110f3  mov     [rsp+58h+psetinfo], 0; psetinfo
0x1800110fc  mov     [rsp+58h+grbit], eax; grbit
0x180011100  mov     [rsp+58h+cbData], ebp; cbData
0x180011104  call    cs:__imp_JetSetColumn
0x18001110b  nop     dword ptr [rax+rax+00h]
0x180011110  test    eax, eax
0x180011112  jnz     short loc_18001116F
0x180011114  mov     rdx, cs:BitmaskTbl; tableid
0x18001111b  xor     r9d, r9d; cbBookmark
0x18001111e  xor     r8d, r8d; pvBookmark
0x180011121  mov     qword ptr [rsp+58h+cbData], 0; pcbActual
0x18001112a  mov     rcx, rsi; sesid
0x18001112d  call    cs:__imp_JetUpdate
0x180011134  nop     dword ptr [rax+rax+00h]
0x180011139  mov     ecx, eax
0x18001113b  lea     rdx, aBitmaskJetupda; "Bitmask : JetUpdate"
0x180011142  mov     r14d, eax
0x180011145  call    DhcpMapJetError
0x18001114a  mov     ebp, eax
0x18001114c  test    r14d, r14d
0x18001114f  jz      short loc_1800111A2
0x180011151  mov     rdx, cs:BitmaskTbl; tableid
0x180011158  mov     r8d, 3; prep
0x18001115e  mov     rcx, rsi; sesid
0x180011161  call    cs:__imp_JetPrepareUpdate
0x180011168  nop     dword ptr [rax+rax+00h]
0x18001116d  jmp     short loc_18001119F
0x18001116f  lea     rdx, aBitmaskJetupda; "Bitmask : JetUpdate"
0x180011176  mov     ecx, eax
0x180011178  call    DhcpMapJetError
0x18001117d  mov     rdx, cs:BitmaskTbl; tableid
0x180011184  mov     r8d, 3; prep
0x18001118a  mov     rcx, rsi; sesid
0x18001118d  mov     ebp, eax
0x18001118f  call    cs:__imp_JetPrepareUpdate
0x180011196  nop     dword ptr [rax+rax+00h]
0x18001119b  lea     r15, [rdi+4]
0x18001119f  mov     r14d, eax
0x1800111a2  test    ebp, ebp
0x1800111a4  jz      short loc_1800111AA
0x1800111a6  mov     eax, ebp
0x1800111a8  jmp     short loc_1800111EB
0x1800111aa  mov     edx, [r15]
0x1800111ad  add     edx, [rbx]
0x1800111af  mov     [r15], edx
0x1800111b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111b9  lea     rax, WPP_GLOBAL_Control
0x1800111c0  cmp     rcx, rax
0x1800111c3  jz      short loc_1800111E9
0x1800111c5  test    dword ptr [rcx+1Ch], 10000000h
0x1800111cc  jz      short loc_1800111E9
0x1800111ce  mov     eax, [rbx]
0x1800111d0  mov     r9d, [rdi]
0x1800111d3  mov     rcx, [rcx+10h]
0x1800111d7  mov     dword ptr [rsp+58h+psetinfo], r14d
0x1800111dc  mov     [rsp+58h+grbit], eax
0x1800111e0  mov     [rsp+58h+cbData], edx
0x1800111e4  call    WPP_SF_DDDd
0x1800111e9  xor     eax, eax
0x1800111eb  mov     rbx, [rsp+58h+arg_0]
0x1800111f0  mov     rbp, [rsp+58h+arg_8]
0x1800111f5  mov     rsi, [rsp+58h+arg_10]
0x1800111fa  add     rsp, 40h
0x1800111fe  pop     r15
0x180011200  pop     r14
0x180011202  pop     rdi
0x180011203  retn
```
