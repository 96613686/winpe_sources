# CScrubDatabase::UpdateColumnData(_SCRUB_PARITY_EXTENT const *)

- ea: `0x18002fbb8`
- end: `0x18002fd2e`
- name: `?UpdateColumnData@CScrubDatabase@@AEAAJPEBU_SCRUB_PARITY_EXTENT@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(CScrubDatabase *__hidden this, const struct _SCRUB_PARITY_EXTENT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18002e820`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x18002fbb8`

## import_xrefs

- `ESENT!JetSetColumns` at `0x18002fcb1`
- `ESENT!JetSetColumns` at `0x18002fcb1`

## string_xrefs

- `0x18002fbef`: `CScrubDatabase::UpdateColumnData`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::UpdateColumnData(CScrubDatabase *this, const struct _SCRUB_PARITY_EXTENT *a2)
{
  __int64 v4; // r9
  JET_TABLEID v5; // rdx
  JET_SESID v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  int v9; // edi
  int v10; // eax
  const char *v12; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v13; // [rsp+48h] [rbp-21h]
  JET_SETCOLUMN psetcolumn; // [rsp+50h] [rbp-19h] BYREF
  int v15; // [rsp+78h] [rbp+Fh]
  char *v16; // [rsp+80h] [rbp+17h]
  int v17; // [rsp+88h] [rbp+1Fh]
  __int128 v18; // [rsp+8Ch] [rbp+23h]
  int v19; // [rsp+9Ch] [rbp+33h]

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v12 = "CScrubDatabase::UpdateColumnData";
  ++*(_WORD *)(v4 + 8);
  *(_QWORD *)(v4 + 16) = "CScrubDatabase::UpdateColumnData";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::UpdateColumnData");
  }
  v5 = *((_QWORD *)this + 3);
  psetcolumn.columnid = *((_DWORD *)this + 8);
  psetcolumn.cbData = 8;
  v15 = *((_DWORD *)this + 9);
  v16 = (char *)a2 + 8;
  v17 = 8;
  v6 = *((_QWORD *)this + 1);
  v19 = 0;
  psetcolumn.pvData = a2;
  memset(&psetcolumn.grbit, 0, 20);
  v18 = 0;
  v7 = JetSetColumns(v6, v5, &psetcolumn, 2u);
  v8 = 0;
  v9 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v7);
    }
    if ( v9 == -1011 )
    {
      v8 = -2147024882;
    }
    else
    {
      v10 = -v9;
      if ( v9 > 0 )
        LOWORD(v10) = v9;
      v8 = v9 & 0x8E5E0000 | (unsigned __int16)v10 | 0xE5E0000;
    }
  }
  v13 = v8;
  CHResultImp::~CHResultImp((CHResultImp *)&v12);
  return v8;
}

```

## disassembly

```asm
0x18002fbb8  push    rbp
0x18002fbba  push    rbx
0x18002fbbb  push    rsi
0x18002fbbc  push    rdi
0x18002fbbd  lea     rbp, [rsp-3Fh]
0x18002fbc2  sub     rsp, 0A8h
0x18002fbc9  mov     r8d, cs:_tls_index
0x18002fbd0  mov     rdi, rdx
0x18002fbd3  mov     rax, gs:58h
0x18002fbdc  mov     rbx, rcx
0x18002fbdf  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002fbe6  mov     edx, 8
0x18002fbeb  mov     r9, [rax+r8*8]
0x18002fbef  lea     r8, aCscrubdatabase_4; "CScrubDatabase::UpdateColumnData"
0x18002fbf6  mov     eax, 10h
0x18002fbfb  mov     [rbp+57h+var_80], r8
0x18002fbff  inc     word ptr [rdx+r9]
0x18002fc04  movzx   edx, word ptr [rdx+r9]
0x18002fc09  mov     [rax+r9], r8
0x18002fc0d  cmp     dx, cx
0x18002fc10  movzx   eax, cx
0x18002fc13  cmovb   ax, dx
0x18002fc17  cmovb   cx, dx
0x18002fc1b  mov     [rbp+57h+var_90], ax
0x18002fc1f  xor     eax, eax
0x18002fc21  mov     [rbp+57h+var_8C], eax
0x18002fc24  mov     rax, cs:off_180047060; "                                       "...
0x18002fc2b  mov     [rbp+57h+var_88], rax
0x18002fc2f  mov     [rbp+57h+var_8E], cx
0x18002fc33  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc3a  lea     rsi, WPP_GLOBAL_Control
0x18002fc41  cmp     rcx, rsi
0x18002fc44  jz      short loc_18002FC69
0x18002fc46  test    byte ptr [rcx+1Ch], 1
0x18002fc4a  jz      short loc_18002FC69
0x18002fc4c  cmp     byte ptr [rcx+19h], 5
0x18002fc50  jb      short loc_18002FC69
0x18002fc52  mov     rcx, [rcx+10h]; LoggerHandle
0x18002fc56  lea     r9, [rbp+57h+var_90]
0x18002fc5a  mov     edx, 0Dh
0x18002fc5f  mov     [rsp+0C0h+var_A0], r8; __int64
0x18002fc64  call    WPP_SF_aZs
0x18002fc69  mov     eax, [rbx+20h]
0x18002fc6c  lea     r8, [rbp+57h+psetcolumn]; psetcolumn
0x18002fc70  mov     rdx, [rbx+18h]; tableid
0x18002fc74  mov     ecx, 8
0x18002fc79  mov     [rbp+57h+psetcolumn.columnid], eax
0x18002fc7c  xorps   xmm0, xmm0
0x18002fc7f  xor     eax, eax
0x18002fc81  mov     [rbp+57h+psetcolumn.cbData], ecx
0x18002fc84  mov     dword ptr [rbp+57h+psetcolumn+24h], eax
0x18002fc87  mov     eax, [rbx+24h]
0x18002fc8a  lea     r9d, [rcx-6]; csetcolumn
0x18002fc8e  mov     [rbp+57h+var_48], eax
0x18002fc91  lea     rax, [rdi+8]
0x18002fc95  mov     [rbp+57h+var_40], rax
0x18002fc99  xor     eax, eax
0x18002fc9b  mov     [rbp+57h+var_38], ecx
0x18002fc9e  mov     rcx, [rbx+8]; sesid
0x18002fca2  mov     [rbp+57h+var_24], eax
0x18002fca5  mov     [rbp+57h+psetcolumn.pvData], rdi
0x18002fca9  movups  xmmword ptr [rbp+57h+psetcolumn.grbit], xmm0
0x18002fcad  movups  [rbp+57h+var_34], xmm0
0x18002fcb1  call    cs:__imp_JetSetColumns
0x18002fcb7  xor     ebx, ebx
0x18002fcb9  mov     edi, eax
0x18002fcbb  test    eax, eax
0x18002fcbd  jz      short loc_18002FD14
0x18002fcbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fcc6  cmp     rcx, rsi
0x18002fcc9  jz      short loc_18002FCED
0x18002fccb  test    byte ptr [rcx+1Ch], 1
0x18002fccf  jz      short loc_18002FCED
0x18002fcd1  cmp     byte ptr [rcx+19h], 2
0x18002fcd5  jb      short loc_18002FCED
0x18002fcd7  mov     rcx, [rcx+10h]
0x18002fcdb  lea     edx, [rbx+3Bh]
0x18002fcde  mov     r9d, eax
0x18002fce1  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002fce8  call    WPP_SF_d
0x18002fced  cmp     edi, 0FFFFFC0Dh
0x18002fcf3  jnz     short loc_18002FCFC
0x18002fcf5  mov     ebx, 8007000Eh
0x18002fcfa  jmp     short loc_18002FD14
0x18002fcfc  mov     eax, edi
0x18002fcfe  neg     eax
0x18002fd00  cmovs   eax, edi
0x18002fd03  and     edi, 8E5E0000h
0x18002fd09  movzx   ebx, ax
0x18002fd0c  or      ebx, edi
0x18002fd0e  or      ebx, 0E5E0000h
0x18002fd14  lea     rcx, [rbp+57h+var_80]; this
0x18002fd18  mov     [rbp+57h+var_78], ebx
0x18002fd1b  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002fd20  mov     eax, ebx
0x18002fd22  add     rsp, 0A8h
0x18002fd29  pop     rdi
0x18002fd2a  pop     rsi
0x18002fd2b  pop     rbx
0x18002fd2c  pop     rbp
0x18002fd2d  retn
```
