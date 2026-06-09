# CScrubDatabase::AddParityExtentRow(_SCRUB_PARITY_EXTENT const *)

- ea: `0x18002e820`
- end: `0x18002eab4`
- name: `?AddParityExtentRow@CScrubDatabase@@AEAAJPEBU_SCRUB_PARITY_EXTENT@@@Z`
- size: `660`
- prototype: `__int64 __fastcall(CScrubDatabase *__hidden this, const struct _SCRUB_PARITY_EXTENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18002fd34`

## callees

- `0x180002e20`
- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x18002e7f0`
- `0x18002e820`
- `0x18002fbb8`
- `0x1800309c8`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18002e91f`
- `ESENT!JetPrepareUpdate` at `0x18002e91f`
- `ESENT!JetUpdate2` at `0x18002ea0f`
- `ESENT!JetUpdate2` at `0x18002ea0f`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::AddParityExtentRow(CScrubDatabase *this, const struct _SCRUB_PARITY_EXTENT *a2)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v6; // r9
  USHORT v7; // dx
  USHORT v8; // ax
  PVOID *v9; // r8
  unsigned int v10; // eax
  int v11; // edi
  unsigned int v12; // ebx
  int v13; // eax
  int updated; // eax
  unsigned int v15; // eax
  int v16; // edi
  int v17; // eax
  const char *v19; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-18h]
  USHORT v21; // [rsp+40h] [rbp-10h]
  USHORT v22; // [rsp+42h] [rbp-Eh]
  int v23; // [rsp+44h] [rbp-Ch]
  char *v24; // [rsp+48h] [rbp-8h]
  __int64 *v25; // [rsp+70h] [rbp+20h] BYREF
  __int64 v26; // [rsp+80h] [rbp+30h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v19 = "CScrubDatabase::AddParityExtentRow";
  v6 = ThreadLocalStoragePointer[tls_index];
  v7 = ++*(_WORD *)(v6 + 8);
  *(_QWORD *)(v6 + 16) = "CScrubDatabase::AddParityExtentRow";
  v8 = Length;
  if ( v7 < Length )
  {
    v8 = v7;
    Length = v7;
  }
  v21 = v8;
  v23 = 0;
  v24 = off_180047060;
  v22 = Length;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::AddParityExtentRow");
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
      WPP_SF_iii(v9[2], 69);
  }
  v10 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v10);
    }
    if ( v11 == -1011 )
    {
      v12 = -2147024882;
    }
    else
    {
      v13 = -v11;
      if ( v11 > 0 )
        LOWORD(v13) = v11;
      v12 = v11 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
    }
    v20 = v12;
  }
  else
  {
    wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v26, (__int64)this);
    v25 = &v26;
    updated = CScrubDatabase::UpdateColumnData(this, a2);
    v20 = updated;
    v12 = updated;
    if ( updated >= 0 )
    {
      v15 = JetUpdate2(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0, 0, 0, 0);
      v16 = v15;
      if ( !v15 )
      {
        v25 = 0;
        v20 = 0;
        CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___::_CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___(&v25);
        v12 = 0;
        goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v15);
      }
      if ( v16 == -1011 )
      {
        v12 = -2147024882;
      }
      else
      {
        v17 = -v16;
        if ( v16 > 0 )
          LOWORD(v17) = v16;
        v12 = v16 & 0x8E5E0000 | (unsigned __int16)v17 | 0xE5E0000;
      }
      v20 = v12;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids,
        (unsigned int)updated);
    }
    CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___::_CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___(&v25);
  }
LABEL_40:
  CHResultImp::~CHResultImp((CHResultImp *)&v19);
  return v12;
}

```

## disassembly

```asm
0x18002e820  mov     [rsp-18h+arg_8], rbx
0x18002e825  mov     [rsp-18h+arg_18], rsi
0x18002e82a  push    rbp
0x18002e82b  push    rdi
0x18002e82c  push    r12
0x18002e82e  mov     rbp, rsp
0x18002e831  sub     rsp, 50h
0x18002e835  mov     rax, gs:58h
0x18002e83e  lea     r10, aCscrubdatabase; "CScrubDatabase::AddParityExtentRow"
0x18002e845  mov     r8d, cs:_tls_index
0x18002e84c  mov     rbx, rdx
0x18002e84f  mov     edx, 8
0x18002e854  mov     rsi, rcx
0x18002e857  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002e85e  mov     [rbp+var_20], r10
0x18002e862  mov     r9, [rax+r8*8]
0x18002e866  mov     eax, 10h
0x18002e86b  inc     word ptr [rdx+r9]
0x18002e870  movzx   edx, word ptr [rdx+r9]
0x18002e875  mov     [rax+r9], r10
0x18002e879  cmp     dx, cx
0x18002e87c  movzx   eax, cx
0x18002e87f  cmovb   ax, dx
0x18002e883  cmovb   cx, dx
0x18002e887  mov     [rbp+var_10], ax
0x18002e88b  xor     eax, eax
0x18002e88d  mov     [rbp+var_C], eax
0x18002e890  mov     rax, cs:off_180047060; "                                       "...
0x18002e897  mov     [rbp+var_8], rax
0x18002e89b  mov     [rbp+var_E], cx
0x18002e89f  mov     r8, cs:WPP_GLOBAL_Control
0x18002e8a6  lea     r12, WPP_GLOBAL_Control
0x18002e8ad  cmp     r8, r12
0x18002e8b0  jz      short loc_18002E914
0x18002e8b2  test    byte ptr [r8+1Ch], 1
0x18002e8b7  jz      short loc_18002E8DE
0x18002e8b9  cmp     byte ptr [r8+19h], 5
0x18002e8be  jb      short loc_18002E8DE
0x18002e8c0  mov     rcx, [r8+10h]; LoggerHandle
0x18002e8c4  lea     r9, [rbp+var_10]
0x18002e8c8  mov     edx, 0Dh
0x18002e8cd  mov     [rsp+50h+pcbActual], r10; __int64
0x18002e8d2  call    WPP_SF_aZs
0x18002e8d7  mov     r8, cs:WPP_GLOBAL_Control
0x18002e8de  cmp     r8, r12
0x18002e8e1  jz      short loc_18002E914
0x18002e8e3  test    byte ptr [r8+1Ch], 1
0x18002e8e8  jz      short loc_18002E914
0x18002e8ea  cmp     byte ptr [r8+19h], 4
0x18002e8ef  jb      short loc_18002E914
0x18002e8f1  mov     rcx, [rbx+8]
0x18002e8f5  mov     edx, 45h ; 'E'
0x18002e8fa  mov     r9, [rbx]
0x18002e8fd  mov     qword ptr [rsp+50h+grbit], rcx
0x18002e902  lea     rax, [r9+rcx]
0x18002e906  mov     rcx, [r8+10h]
0x18002e90a  mov     [rsp+50h+pcbActual], rax
0x18002e90f  call    WPP_SF_iii
0x18002e914  mov     rdx, [rsi+18h]; tableid
0x18002e918  xor     r8d, r8d; prep
0x18002e91b  mov     rcx, [rsi+8]; sesid
0x18002e91f  call    cs:__imp_JetPrepareUpdate
0x18002e925  mov     edi, eax
0x18002e927  test    eax, eax
0x18002e929  jz      short loc_18002E98A
0x18002e92b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e932  cmp     rcx, r12
0x18002e935  jz      short loc_18002E95B
0x18002e937  test    byte ptr [rcx+1Ch], 1
0x18002e93b  jz      short loc_18002E95B
0x18002e93d  cmp     byte ptr [rcx+19h], 2
0x18002e941  jb      short loc_18002E95B
0x18002e943  mov     rcx, [rcx+10h]
0x18002e947  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002e94e  mov     edx, 46h ; 'F'
0x18002e953  mov     r9d, eax
0x18002e956  call    WPP_SF_d
0x18002e95b  cmp     edi, 0FFFFFC0Dh
0x18002e961  jnz     short loc_18002E96A
0x18002e963  mov     ebx, 8007000Eh
0x18002e968  jmp     short loc_18002E982
0x18002e96a  mov     eax, edi
0x18002e96c  neg     eax
0x18002e96e  cmovs   eax, edi
0x18002e971  and     edi, 8E5E0000h
0x18002e977  movzx   ebx, ax
0x18002e97a  or      ebx, edi
0x18002e97c  or      ebx, 0E5E0000h
0x18002e982  mov     [rbp+var_18], ebx
0x18002e985  jmp     loc_18002EA94
0x18002e98a  mov     rdx, rsi
0x18002e98d  lea     rcx, [rbp+arg_10]
0x18002e991  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18002e996  lea     rcx, [rbp+arg_10]
0x18002e99a  mov     rdx, rbx; struct _SCRUB_PARITY_EXTENT *
0x18002e99d  mov     [rbp+arg_0], rcx
0x18002e9a1  mov     rcx, rsi; this
0x18002e9a4  call    ?UpdateColumnData@CScrubDatabase@@AEAAJPEBU_SCRUB_PARITY_EXTENT@@@Z; CScrubDatabase::UpdateColumnData(_SCRUB_PARITY_EXTENT const *)
0x18002e9a9  mov     [rbp+var_18], eax
0x18002e9ac  mov     ebx, eax
0x18002e9ae  test    eax, eax
0x18002e9b0  jns     short loc_18002E9F0
0x18002e9b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9b9  cmp     rcx, r12
0x18002e9bc  jz      short loc_18002E9E2
0x18002e9be  test    byte ptr [rcx+1Ch], 1
0x18002e9c2  jz      short loc_18002E9E2
0x18002e9c4  cmp     byte ptr [rcx+19h], 2
0x18002e9c8  jb      short loc_18002E9E2
0x18002e9ca  mov     rcx, [rcx+10h]
0x18002e9ce  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002e9d5  mov     edx, 47h ; 'G'
0x18002e9da  mov     r9d, eax
0x18002e9dd  call    WPP_SF_d
0x18002e9e2  lea     rcx, [rbp+arg_0]
0x18002e9e6  call    CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810______CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___
0x18002e9eb  jmp     loc_18002EA94
0x18002e9f0  mov     rdx, [rsi+18h]; tableid
0x18002e9f4  xor     r9d, r9d; cbBookmark
0x18002e9f7  mov     rcx, [rsi+8]; sesid
0x18002e9fb  xor     r8d, r8d; pvBookmark
0x18002e9fe  mov     [rsp+50h+grbit], 0; grbit
0x18002ea06  mov     [rsp+50h+pcbActual], 0; pcbActual
0x18002ea0f  call    cs:__imp_JetUpdate2
0x18002ea15  mov     edi, eax
0x18002ea17  test    eax, eax
0x18002ea19  jz      short loc_18002EA7A
0x18002ea1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea22  cmp     rcx, r12
0x18002ea25  jz      short loc_18002EA4B
0x18002ea27  test    byte ptr [rcx+1Ch], 1
0x18002ea2b  jz      short loc_18002EA4B
0x18002ea2d  cmp     byte ptr [rcx+19h], 2
0x18002ea31  jb      short loc_18002EA4B
0x18002ea33  mov     rcx, [rcx+10h]
0x18002ea37  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002ea3e  mov     edx, 48h ; 'H'
0x18002ea43  mov     r9d, eax
0x18002ea46  call    WPP_SF_d
0x18002ea4b  cmp     edi, 0FFFFFC0Dh
0x18002ea51  jnz     short loc_18002EA5A
0x18002ea53  mov     ebx, 8007000Eh
0x18002ea58  jmp     short loc_18002EA72
0x18002ea5a  mov     eax, edi
0x18002ea5c  neg     eax
0x18002ea5e  cmovs   eax, edi
0x18002ea61  and     edi, 8E5E0000h
0x18002ea67  movzx   ebx, ax
0x18002ea6a  or      ebx, edi
0x18002ea6c  or      ebx, 0E5E0000h
0x18002ea72  mov     [rbp+var_18], ebx
0x18002ea75  jmp     loc_18002E9E2
0x18002ea7a  lea     rcx, [rbp+arg_0]
0x18002ea7e  mov     [rbp+arg_0], 0
0x18002ea86  mov     [rbp+var_18], 0
0x18002ea8d  call    CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810______CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___
0x18002ea92  xor     ebx, ebx
0x18002ea94  lea     rcx, [rbp+var_20]; this
0x18002ea98  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002ea9d  lea     r11, [rsp+50h+var_s0]
0x18002eaa2  mov     eax, ebx
0x18002eaa4  mov     rbx, [r11+28h]
0x18002eaa8  mov     rsi, [r11+38h]
0x18002eaac  mov     rsp, r11
0x18002eaaf  pop     r12
0x18002eab1  pop     rdi
0x18002eab2  pop     rbp
0x18002eab3  retn
```
