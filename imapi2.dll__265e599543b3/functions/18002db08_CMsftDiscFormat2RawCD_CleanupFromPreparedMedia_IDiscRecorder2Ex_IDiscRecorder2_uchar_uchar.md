# CMsftDiscFormat2RawCD::CleanupFromPreparedMedia(IDiscRecorder2Ex *,IDiscRecorder2 *,uchar,uchar)

- ea: `0x18002db08`
- end: `0x18002dded`
- name: `?CleanupFromPreparedMedia@CMsftDiscFormat2RawCD@@AEAAXPEAUIDiscRecorder2Ex@@PEAUIDiscRecorder2@@EE@Z`
- size: `741`
- prototype: `void __usercall(CMsftDiscFormat2RawCD *__hidden this@<rcx>, struct IDiscRecorder2Ex *@<rdx>, struct IDiscRecorder2 *@<r8>, unsigned __int8@<r9b>, unsigned __int8)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002e210`
- `0x18002ea20`
- `0x18002f540`
- `0x18002fcf0`

## callees

- `0x1800140f4`
- `0x18001724c`
- `0x18002db08`
- `0x18002fdc8`
- `0x1800464ec`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002dd55`
- `ole32!CoTaskMemFree` at `0x18002dd77`
- `ole32!CoTaskMemFree` at `0x18002dd55`
- `ole32!CoTaskMemFree` at `0x18002dd77`

## pseudocode

```c
void __fastcall CMsftDiscFormat2RawCD::CleanupFromPreparedMedia(
        CMsftDiscFormat2RawCD *this,
        struct IDiscRecorder2Ex *a2,
        struct IDiscRecorder2 *a3,
        unsigned __int8 a4,
        unsigned __int8 a5)
{
  unsigned int v8; // edi
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // edi
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // edi
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  struct IUnknown *v20; // rcx
  int v21; // eax
  void *v22; // rcx
  void *v23; // rcx
  __int64 v24; // rcx

  v8 = 0;
  while ( v8 < 5 )
  {
    v9 = CMsftDiscFormat2RawCD::RestoreWriteParametersModePage(this, a2);
    if ( v9 >= 0 )
      goto LABEL_15;
    if ( v8 == 4 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 2u )
      {
        v11 = 109;
LABEL_9:
        WPP_SF_d(v10[47], v11, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)v9);
      }
      ++v8;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
      {
        v11 = 110;
        goto LABEL_9;
      }
LABEL_15:
      ++v8;
      if ( v9 >= 0 )
        break;
    }
  }
  if ( a4 )
  {
    v12 = 0;
    while ( v12 < 5 )
    {
      v13 = Imapi2Utility::PreventAllowMediumRemoval((Imapi2Utility *)a2, 0, (unsigned __int8)a3, a4);
      if ( v13 >= 0 )
        goto LABEL_31;
      if ( v12 == 4 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 2u )
        {
          v15 = 111;
LABEL_25:
          WPP_SF_d(v14[47], v15, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)v13);
        }
        ++v12;
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
        {
          v15 = 112;
          goto LABEL_25;
        }
LABEL_31:
        ++v12;
        if ( v13 >= 0 )
          break;
      }
    }
  }
  if ( a5 )
  {
    v16 = 0;
    while ( v16 < 5 )
    {
      v17 = ((__int64 (__fastcall *)(struct IDiscRecorder2 *))a3->lpVtbl->ReleaseExclusiveAccess)(a3);
      if ( v17 >= 0 )
        goto LABEL_47;
      if ( v16 == 4 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 2u )
        {
          v19 = 113;
LABEL_41:
          WPP_SF_d(v18[47], v19, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)v17);
        }
        ++v16;
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
        {
          v19 = 114;
          goto LABEL_41;
        }
LABEL_47:
        ++v16;
        if ( v17 >= 0 )
          break;
      }
    }
  }
  v20 = (struct IUnknown *)*((_QWORD *)this + 34);
  if ( v20 )
  {
    v21 = ATL::AtlUnadvise(v20, (const struct _GUID *)a2, *((_DWORD *)this + 23));
    *((_DWORD *)this + 23) = -16843010;
    if ( v21 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 47),
        115,
        &WPP_465922b870433540ecd6931719c7292a_Traceguids,
        (unsigned int)v21);
    }
  }
  v22 = (void *)*((_QWORD *)this + 30);
  *((_DWORD *)this + 58) = 0;
  CoTaskMemFree(v22);
  v23 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 30) = 0;
  *((_DWORD *)this + 62) = 0;
  CoTaskMemFree(v23);
  v24 = *((_QWORD *)this + 34);
  *((_QWORD *)this + 32) = 0;
  *((_DWORD *)this + 66) = 0;
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    *((_QWORD *)this + 34) = 0;
  }
  *((_WORD *)this + 106) = 0;
  *((_WORD *)this + 96) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 52) = -1;
}

```

## disassembly

```asm
0x18002db08  mov     [rsp+arg_0], rbx
0x18002db0d  mov     [rsp+arg_8], rbp
0x18002db12  mov     [rsp+arg_10], r8
0x18002db17  push    rsi
0x18002db18  push    rdi
0x18002db19  push    r14
0x18002db1b  sub     rsp, 20h
0x18002db1f  mov     sil, r9b
0x18002db22  lea     r14, WPP_GLOBAL_Control
0x18002db29  mov     rbp, rdx
0x18002db2c  mov     rbx, rcx
0x18002db2f  xor     edi, edi
0x18002db31  cmp     edi, 5
0x18002db34  jnb     short loc_18002DBB0
0x18002db36  mov     rdx, rbp; struct IDiscRecorder2Ex *
0x18002db39  mov     rcx, rbx; this
0x18002db3c  call    ?RestoreWriteParametersModePage@CMsftDiscFormat2RawCD@@AEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscFormat2RawCD::RestoreWriteParametersModePage(IDiscRecorder2Ex *)
0x18002db41  test    eax, eax
0x18002db43  jns     short loc_18002DBAA
0x18002db45  cmp     edi, 4
0x18002db48  jnz     short loc_18002DB85
0x18002db4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db51  cmp     rcx, r14
0x18002db54  jz      short loc_18002DB81
0x18002db56  test    [rcx+184h], dil
0x18002db5d  jz      short loc_18002DB81
0x18002db5f  cmp     byte ptr [rcx+181h], 2
0x18002db66  jb      short loc_18002DB81
0x18002db68  lea     edx, [rdi+69h]
0x18002db6b  mov     rcx, [rcx+178h]
0x18002db72  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002db79  mov     r9d, eax
0x18002db7c  call    WPP_SF_d
0x18002db81  inc     edi
0x18002db83  jmp     short loc_18002DB31
0x18002db85  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db8c  cmp     rcx, r14
0x18002db8f  jz      short loc_18002DBAA
0x18002db91  test    byte ptr [rcx+184h], 4
0x18002db98  jz      short loc_18002DBAA
0x18002db9a  cmp     byte ptr [rcx+181h], 3
0x18002dba1  jb      short loc_18002DBAA
0x18002dba3  mov     edx, 6Eh ; 'n'
0x18002dba8  jmp     short loc_18002DB6B
0x18002dbaa  inc     edi
0x18002dbac  test    eax, eax
0x18002dbae  js      short loc_18002DB31
0x18002dbb0  mov     r14, [rsp+38h+arg_10]
0x18002dbb5  test    sil, sil
0x18002dbb8  jz      loc_18002DC45
0x18002dbbe  xor     edi, edi
0x18002dbc0  lea     rsi, WPP_GLOBAL_Control
0x18002dbc7  cmp     edi, 5
0x18002dbca  jnb     short loc_18002DC45
0x18002dbcc  xor     edx, edx; struct IDiscRecorder2Ex *
0x18002dbce  mov     rcx, rbp; this
0x18002dbd1  call    ?PreventAllowMediumRemoval@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EE@Z; Imapi2Utility::PreventAllowMediumRemoval(IDiscRecorder2Ex *,uchar,uchar)
0x18002dbd6  test    eax, eax
0x18002dbd8  jns     short loc_18002DC3F
0x18002dbda  cmp     edi, 4
0x18002dbdd  jnz     short loc_18002DC1A
0x18002dbdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbe6  cmp     rcx, rsi
0x18002dbe9  jz      short loc_18002DC16
0x18002dbeb  test    [rcx+184h], dil
0x18002dbf2  jz      short loc_18002DC16
0x18002dbf4  cmp     byte ptr [rcx+181h], 2
0x18002dbfb  jb      short loc_18002DC16
0x18002dbfd  lea     edx, [rdi+6Bh]
0x18002dc00  mov     rcx, [rcx+178h]
0x18002dc07  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002dc0e  mov     r9d, eax
0x18002dc11  call    WPP_SF_d
0x18002dc16  inc     edi
0x18002dc18  jmp     short loc_18002DBC7
0x18002dc1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc21  cmp     rcx, rsi
0x18002dc24  jz      short loc_18002DC3F
0x18002dc26  test    byte ptr [rcx+184h], 4
0x18002dc2d  jz      short loc_18002DC3F
0x18002dc2f  cmp     byte ptr [rcx+181h], 3
0x18002dc36  jb      short loc_18002DC3F
0x18002dc38  mov     edx, 70h ; 'p'
0x18002dc3d  jmp     short loc_18002DC00
0x18002dc3f  inc     edi
0x18002dc41  test    eax, eax
0x18002dc43  js      short loc_18002DBC7
0x18002dc45  cmp     [rsp+38h+arg_20], 0
0x18002dc4a  jz      loc_18002DCE4
0x18002dc50  xor     edi, edi
0x18002dc52  lea     rsi, WPP_GLOBAL_Control
0x18002dc59  cmp     edi, 5
0x18002dc5c  jnb     loc_18002DCE4
0x18002dc62  mov     rax, [r14]
0x18002dc65  mov     rcx, r14
0x18002dc68  mov     rax, [rax+50h]
0x18002dc6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc71  test    eax, eax
0x18002dc73  jns     short loc_18002DCDA
0x18002dc75  cmp     edi, 4
0x18002dc78  jnz     short loc_18002DCB5
0x18002dc7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc81  cmp     rcx, rsi
0x18002dc84  jz      short loc_18002DCB1
0x18002dc86  test    [rcx+184h], dil
0x18002dc8d  jz      short loc_18002DCB1
0x18002dc8f  cmp     byte ptr [rcx+181h], 2
0x18002dc96  jb      short loc_18002DCB1
0x18002dc98  lea     edx, [rdi+6Dh]
0x18002dc9b  mov     rcx, [rcx+178h]
0x18002dca2  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002dca9  mov     r9d, eax
0x18002dcac  call    WPP_SF_d
0x18002dcb1  inc     edi
0x18002dcb3  jmp     short loc_18002DC59
0x18002dcb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dcbc  cmp     rcx, rsi
0x18002dcbf  jz      short loc_18002DCDA
0x18002dcc1  test    byte ptr [rcx+184h], 4
0x18002dcc8  jz      short loc_18002DCDA
0x18002dcca  cmp     byte ptr [rcx+181h], 3
0x18002dcd1  jb      short loc_18002DCDA
0x18002dcd3  mov     edx, 72h ; 'r'
0x18002dcd8  jmp     short loc_18002DC9B
0x18002dcda  inc     edi
0x18002dcdc  test    eax, eax
0x18002dcde  js      loc_18002DC59
0x18002dce4  mov     rcx, [rbx+110h]; struct IUnknown *
0x18002dceb  test    rcx, rcx
0x18002dcee  jz      short loc_18002DD44
0x18002dcf0  mov     r8d, [rbx+5Ch]; unsigned int
0x18002dcf4  call    ?AtlUnadvise@ATL@@YAJPEAUIUnknown@@AEBU_GUID@@K@Z; ATL::AtlUnadvise(IUnknown *,_GUID const &,ulong)
0x18002dcf9  mov     dword ptr [rbx+5Ch], 0FEFEFEFEh
0x18002dd00  test    eax, eax
0x18002dd02  jns     short loc_18002DD44
0x18002dd04  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd0b  lea     rdx, WPP_GLOBAL_Control
0x18002dd12  cmp     rcx, rdx
0x18002dd15  jz      short loc_18002DD44
0x18002dd17  test    byte ptr [rcx+184h], 4
0x18002dd1e  jz      short loc_18002DD44
0x18002dd20  cmp     byte ptr [rcx+181h], 3
0x18002dd27  jb      short loc_18002DD44
0x18002dd29  mov     rcx, [rcx+178h]
0x18002dd30  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002dd37  mov     edx, 73h ; 's'
0x18002dd3c  mov     r9d, eax
0x18002dd3f  call    WPP_SF_d
0x18002dd44  mov     rcx, [rbx+0F0h]; pv
0x18002dd4b  mov     dword ptr [rbx+0E8h], 0
0x18002dd55  call    cs:__imp_CoTaskMemFree
0x18002dd5b  mov     rcx, [rbx+100h]; pv
0x18002dd62  mov     qword ptr [rbx+0F0h], 0
0x18002dd6d  mov     dword ptr [rbx+0F8h], 0
0x18002dd77  call    cs:__imp_CoTaskMemFree
0x18002dd7d  mov     rcx, [rbx+110h]
0x18002dd84  mov     qword ptr [rbx+100h], 0
0x18002dd8f  mov     dword ptr [rbx+108h], 0
0x18002dd99  test    rcx, rcx
0x18002dd9c  jz      short loc_18002DDB5
0x18002dd9e  mov     rax, [rcx]
0x18002dda1  mov     rax, [rax+10h]
0x18002dda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddaa  mov     qword ptr [rbx+110h], 0
0x18002ddb5  mov     rbp, [rsp+38h+arg_8]
0x18002ddba  xor     eax, eax
0x18002ddbc  mov     [rbx+0D4h], ax
0x18002ddc3  mov     [rbx+0C0h], ax
0x18002ddca  mov     qword ptr [rbx+118h], 0
0x18002ddd5  mov     dword ptr [rbx+0D0h], 0FFFFFFFFh
0x18002dddf  mov     rbx, [rsp+38h+arg_0]
0x18002dde4  add     rsp, 20h
0x18002dde8  pop     r14
0x18002ddea  pop     rdi
0x18002ddeb  pop     rsi
0x18002ddec  retn
```
