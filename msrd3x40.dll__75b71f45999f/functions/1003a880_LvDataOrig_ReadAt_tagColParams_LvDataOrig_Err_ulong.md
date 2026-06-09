# LvDataOrig::ReadAt(tagColParams *,LvDataOrig *,Err &,ulong *)

- ea: `0x1003a880`
- end: `0x1003ab6e`
- name: `?ReadAt@LvDataOrig@@UAEKPAUtagColParams@@PAV1@AAVErr@@PAK@Z`
- size: `750`
- prototype: `unsigned int __thiscall(LvDataOrig *__hidden this, struct tagColParams *, struct LvDataOrig *, struct Err *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x10010580`
- `0x10025ee0`
- `0x10026060`
- `0x1003a790`
- `0x1003a880`
- `0x1003ab80`
- `0x1003b970`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
size_t __thiscall LvDataOrig::ReadAt(
        LvDataOrig *this,
        struct tagColParams *a2,
        struct LvDataOrig *a3,
        struct Err *a4,
        unsigned int *a5)
{
  size_t v6; // esi
  Err *v7; // edx
  int v8; // eax
  unsigned int v10; // eax
  struct tagColParams *v11; // ecx
  unsigned int v12; // edi
  struct tagColParams *v13; // eax
  Err *v14; // edx
  struct tagColParams *v15; // eax
  size_t v16; // ecx
  size_t v17; // ecx
  unsigned int v18; // ecx
  struct Err *v19; // edx
  size_t v20; // eax
  unsigned int v21; // eax
  int v22; // [esp+10h] [ebp-40h] BYREF
  int v23; // [esp+14h] [ebp-3Ch]
  size_t v24; // [esp+20h] [ebp-30h]
  unsigned int v25; // [esp+24h] [ebp-2Ch]
  int v26; // [esp+28h] [ebp-28h]
  int v27; // [esp+2Ch] [ebp-24h]
  unsigned int v28; // [esp+30h] [ebp-20h] BYREF
  int v29; // [esp+34h] [ebp-1Ch]
  struct tagColParams *v30; // [esp+38h] [ebp-18h]
  size_t Size; // [esp+3Ch] [ebp-14h]
  unsigned int v32; // [esp+40h] [ebp-10h]
  int v33; // [esp+4Ch] [ebp-4h]

  v6 = 0;
  if ( a5 )
    *a5 = 0;
  LvDataOrig::CheckDataHasChanged(this, a2);
  if ( *((_DWORD *)this + 515) )
  {
    if ( !*((_DWORD *)this + 523) )
    {
      v7 = a4;
      goto LABEL_13;
    }
    Err::SetWarning(a4, 1004);
    return 0;
  }
  LvDataOrig::GetRecordData(this, (int)a2, 1, a4);
  v7 = a4;
  v8 = *(_DWORD *)a4;
  if ( (*(_DWORD *)a4 & 8) != 0 || (v8 & 4) != 0 && (v8 & 1) == 0 && *((_DWORD *)a4 + 1) == 1004 )
    return 0;
LABEL_13:
  if ( a5 )
    *a5 = *((_DWORD *)this + 516);
  v10 = *((_DWORD *)this + 516);
  v11 = a2;
  v12 = *((_DWORD *)a2 + 4);
  if ( v12 >= v10 )
    return 0;
  if ( !*((_DWORD *)a2 + 2) && v10 )
  {
    Err::SetWarning(v7, 1006);
    return 0;
  }
  if ( !*((_DWORD *)this + 514) )
  {
    v22 = 0;
    v23 = 0;
    v33 = 0;
    v13 = (struct tagColParams *)LvDataOrig::ReadDPOfOffset(this, a2, v12, (struct DataPage *)&v22, &v28, v7);
    v14 = a4;
    v30 = v13;
    if ( (*(_BYTE *)a4 & 8) != 0 )
    {
LABEL_48:
      v15 = a2;
LABEL_49:
      if ( v6 == *((_DWORD *)v15 + 2) && v12 != *((_DWORD *)this + 516) )
        Err::SetWarning(v14, 1006);
      if ( v22 )
        --*(_WORD *)(v22 + 76);
      return v6;
    }
    while ( 1 )
    {
      v15 = a2;
      if ( v12 >= *((_DWORD *)this + 516) )
        goto LABEL_49;
      v16 = *((_DWORD *)a2 + 2);
      if ( v6 >= v16 )
        goto LABEL_49;
      v17 = v16 - v6;
      if ( v17 >= *((_DWORD *)this + 516) - v12 )
        v17 = *((_DWORD *)this + 516) - v12;
      Size = v17;
      v18 = 2032 - (unsigned __int16)(v12 - (_WORD)v30);
      v29 = (unsigned __int16)(v12 - (_WORD)v30);
      v27 = (unsigned __int8)v28;
      if ( Size < v18 )
        v18 = Size;
      v19 = a4;
      v26 = *(unsigned __int16 *)(v23 + 2 * (unsigned __int8)v28 + 10);
      v32 = v18;
      Size = v26 & 0x3FFF;
      if ( Size <= 0x800 )
      {
        if ( v27 )
        {
          v18 = v32;
          v20 = *(_WORD *)(v23 + 2 * v27 + 8) & 0x3FFF;
          if ( v20 > 0x800 || Size > v20 )
            goto LABEL_37;
        }
        else
        {
          v20 = 2048;
        }
        v21 = v20 - Size;
        v18 = v32;
        if ( v21 <= 0x800 )
        {
          v19 = a4;
          v25 = v21;
          v24 = Size + v23;
          v18 = v32;
          if ( (v26 & 0xFFFFC000) == 0xC000 )
          {
            Err::SetError(a4, -1017, v32);
LABEL_47:
            v14 = a4;
            goto LABEL_48;
          }
        }
      }
LABEL_37:
      if ( v25 - v29 - 4 < v18 )
      {
        Err::SetError(v19, -1611, v18);
        goto LABEL_47;
      }
      memcpy((void *)(v6 + *((_DWORD *)a2 + 1)), (const void *)(v24 + 4 + v29), v18);
      v12 += v32;
      v6 += v32;
      v15 = a2;
      if ( v12 < *((_DWORD *)this + 516) && v6 < *((_DWORD *)a2 + 2) )
      {
        if ( v12 >= (unsigned int)v30 + 2032 )
          v30 = (struct tagColParams *)LvDataOrig::ReadDPOfOffset(this, v30, v12, (struct DataPage *)&v22, &v28, a4);
        v15 = a2;
      }
      v14 = a4;
      if ( (*(_BYTE *)a4 & 8) != 0 )
        goto LABEL_49;
    }
  }
  v6 = v10 - v12;
  if ( *((_DWORD *)a2 + 2) < v10 - v12 )
  {
    Err::SetWarning(v7, 1006);
    v11 = a2;
    v6 = *((_DWORD *)a2 + 2);
  }
  memcpy(*((void **)v11 + 1), (char *)this + *((_DWORD *)v11 + 4) + 4, v6);
  return v6;
}

```

## disassembly

```asm
0x1003a880  mov     edi, edi
0x1003a882  push    ebp
0x1003a883  mov     ebp, esp
0x1003a885  push    0FFFFFFFFh
0x1003a887  push    offset ?ReadAt@LvDataOrig@@UAEKPAUtagColParams@@PAV1@AAVErr@@PAK@Z_SEH
0x1003a88c  mov     eax, large fs:0
0x1003a892  push    eax
0x1003a893  sub     esp, 34h
0x1003a896  push    ebx
0x1003a897  push    esi
0x1003a898  push    edi
0x1003a899  mov     eax, ___security_cookie
0x1003a89e  xor     eax, ebp
0x1003a8a0  push    eax
0x1003a8a1  lea     eax, [ebp+var_C]
0x1003a8a4  mov     large fs:0, eax
0x1003a8aa  mov     ebx, ecx
0x1003a8ac  mov     eax, [ebp+arg_C]
0x1003a8af  xor     esi, esi
0x1003a8b1  test    eax, eax
0x1003a8b3  jz      short loc_1003A8B7
0x1003a8b5  mov     [eax], esi
0x1003a8b7  mov     edi, [ebp+arg_0]
0x1003a8ba  push    edi; struct tagColParams *
0x1003a8bb  call    ?CheckDataHasChanged@LvDataOrig@@QAEXPAUtagColParams@@@Z; LvDataOrig::CheckDataHasChanged(tagColParams *)
0x1003a8c0  cmp     [ebx+80Ch], esi
0x1003a8c6  jnz     short loc_1003A8F1
0x1003a8c8  push    [ebp+arg_8]
0x1003a8cb  mov     ecx, ebx
0x1003a8cd  push    1
0x1003a8cf  push    edi
0x1003a8d0  call    ?GetRecordData@LvDataOrig@@QAEXPAUtagColParams@@W4LvNullWarningAction@@AAVErr@@@Z; LvDataOrig::GetRecordData(tagColParams *,LvNullWarningAction,Err &)
0x1003a8d5  mov     edx, [ebp+arg_8]
0x1003a8d8  mov     eax, [edx]
0x1003a8da  test    al, 8
0x1003a8dc  jnz     short loc_1003A906
0x1003a8de  test    al, 4
0x1003a8e0  jz      short loc_1003A91F
0x1003a8e2  test    al, 1
0x1003a8e4  jnz     short loc_1003A91F
0x1003a8e6  cmp     dword ptr [edx+4], 3ECh
0x1003a8ed  jz      short loc_1003A906
0x1003a8ef  jmp     short loc_1003A91F
0x1003a8f1  cmp     [ebx+82Ch], esi
0x1003a8f7  jz      short loc_1003A91C
0x1003a8f9  mov     ecx, [ebp+arg_8]; this
0x1003a8fc  push    3ECh; int
0x1003a901  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1003a906  xor     eax, eax
0x1003a908  mov     ecx, [ebp+var_C]
0x1003a90b  mov     large fs:0, ecx
0x1003a912  pop     ecx
0x1003a913  pop     edi
0x1003a914  pop     esi
0x1003a915  pop     ebx
0x1003a916  mov     esp, ebp
0x1003a918  pop     ebp
0x1003a919  retn    10h
0x1003a91c  mov     edx, [ebp+arg_8]
0x1003a91f  mov     ecx, [ebp+arg_C]
0x1003a922  test    ecx, ecx
0x1003a924  jz      short loc_1003A92E
0x1003a926  mov     eax, [ebx+810h]
0x1003a92c  mov     [ecx], eax
0x1003a92e  mov     eax, [ebx+810h]
0x1003a934  mov     ecx, edi
0x1003a936  mov     edi, [ecx+10h]
0x1003a939  cmp     edi, eax
0x1003a93b  jnb     short loc_1003A906
0x1003a93d  cmp     [ecx+8], esi
0x1003a940  jnz     short loc_1003A968
0x1003a942  test    eax, eax
0x1003a944  jz      short loc_1003A968
0x1003a946  push    3EEh; int
0x1003a94b  mov     ecx, edx; this
0x1003a94d  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1003a952  xor     eax, eax
0x1003a954  mov     ecx, [ebp+var_C]
0x1003a957  mov     large fs:0, ecx
0x1003a95e  pop     ecx
0x1003a95f  pop     edi
0x1003a960  pop     esi
0x1003a961  pop     ebx
0x1003a962  mov     esp, ebp
0x1003a964  pop     ebp
0x1003a965  retn    10h
0x1003a968  cmp     [ebx+808h], esi
0x1003a96e  jz      short loc_1003A9A5
0x1003a970  mov     esi, eax
0x1003a972  sub     esi, edi
0x1003a974  cmp     [ecx+8], esi
0x1003a977  jnb     short loc_1003A98B
0x1003a979  push    3EEh; int
0x1003a97e  mov     ecx, edx; this
0x1003a980  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1003a985  mov     ecx, [ebp+arg_0]
0x1003a988  mov     esi, [ecx+8]
0x1003a98b  mov     eax, [ecx+10h]
0x1003a98e  add     eax, 4
0x1003a991  push    esi; Size
0x1003a992  add     eax, ebx
0x1003a994  push    eax; Src
0x1003a995  push    dword ptr [ecx+4]; void *
0x1003a998  call    _memcpy
0x1003a99d  add     esp, 0Ch
0x1003a9a0  jmp     loc_1003AB58
0x1003a9a5  mov     [ebp+var_40], esi
0x1003a9a8  mov     [ebp+var_3C], esi
0x1003a9ab  push    edx; struct Err *
0x1003a9ac  lea     eax, [ebp+var_20]
0x1003a9af  mov     [ebp+var_4], 0
0x1003a9b6  push    eax; unsigned int *
0x1003a9b7  lea     eax, [ebp+var_40]
0x1003a9ba  push    eax; struct DataPage *
0x1003a9bb  push    edi; unsigned int
0x1003a9bc  push    ecx; struct tagColParams *
0x1003a9bd  mov     ecx, ebx; this
0x1003a9bf  call    ?ReadDPOfOffset@LvDataOrig@@AAEKPAUtagColParams@@KAAVDataPage@@PAKAAVErr@@@Z; LvDataOrig::ReadDPOfOffset(tagColParams *,ulong,DataPage &,ulong *,Err &)
0x1003a9c4  mov     edx, [ebp+arg_8]
0x1003a9c7  mov     [ebp+var_18], eax
0x1003a9ca  test    byte ptr [edx], 8
0x1003a9cd  jnz     loc_1003AB31
0x1003a9d3  nop     dword ptr [eax+00h]
0x1003a9d7  nop     word ptr [eax+eax+00000000h]
0x1003a9e0  mov     eax, [ebp+arg_0]
0x1003a9e3  cmp     edi, [ebx+810h]
0x1003a9e9  jnb     loc_1003AB34
0x1003a9ef  mov     ecx, [eax+8]
0x1003a9f2  cmp     esi, ecx
0x1003a9f4  jnb     loc_1003AB34
0x1003a9fa  mov     eax, [ebx+810h]
0x1003aa00  sub     ecx, esi
0x1003aa02  mov     edx, [ebp+var_3C]
0x1003aa05  sub     eax, edi
0x1003aa07  cmp     ecx, eax
0x1003aa09  cmovnb  ecx, eax
0x1003aa0c  mov     eax, edi
0x1003aa0e  sub     eax, [ebp+var_18]
0x1003aa11  mov     [ebp+Size], ecx
0x1003aa14  mov     ecx, 7F0h
0x1003aa19  movzx   eax, ax
0x1003aa1c  sub     ecx, eax
0x1003aa1e  mov     [ebp+var_1C], eax
0x1003aa21  movzx   eax, byte ptr [ebp+var_20]
0x1003aa25  cmp     [ebp+Size], ecx
0x1003aa28  mov     [ebp+var_24], eax
0x1003aa2b  cmovb   ecx, [ebp+Size]
0x1003aa2f  movzx   eax, word ptr [edx+eax*2+0Ah]
0x1003aa34  mov     edx, [ebp+arg_8]
0x1003aa37  mov     [ebp+var_28], eax
0x1003aa3a  and     eax, 3FFFh
0x1003aa3f  mov     [ebp+var_10], ecx
0x1003aa42  mov     [ebp+Size], eax
0x1003aa45  cmp     eax, 800h
0x1003aa4a  ja      short loc_1003AAA4
0x1003aa4c  mov     eax, [ebp+var_24]
0x1003aa4f  test    eax, eax
0x1003aa51  jnz     short loc_1003AA5A
0x1003aa53  mov     eax, 800h
0x1003aa58  jmp     short loc_1003AA76
0x1003aa5a  mov     ecx, [ebp+var_3C]
0x1003aa5d  movzx   eax, word ptr [ecx+eax*2+8]
0x1003aa62  mov     ecx, [ebp+var_10]
0x1003aa65  and     eax, 3FFFh
0x1003aa6a  cmp     eax, 800h
0x1003aa6f  ja      short loc_1003AAA4
0x1003aa71  cmp     [ebp+Size], eax
0x1003aa74  ja      short loc_1003AAA4
0x1003aa76  sub     eax, [ebp+Size]
0x1003aa79  mov     ecx, [ebp+var_10]
0x1003aa7c  cmp     eax, 800h
0x1003aa81  ja      short loc_1003AAA4
0x1003aa83  mov     ecx, [ebp+var_3C]
0x1003aa86  add     ecx, [ebp+Size]
0x1003aa89  mov     edx, [ebp+arg_8]
0x1003aa8c  mov     [ebp+var_2C], eax
0x1003aa8f  mov     eax, [ebp+var_28]
0x1003aa92  and     eax, 0FFFFC000h
0x1003aa97  mov     [ebp+var_30], ecx
0x1003aa9a  mov     ecx, [ebp+var_10]
0x1003aa9d  cmp     eax, 0C000h
0x1003aaa2  jz      short loc_1003AB1A
0x1003aaa4  mov     eax, [ebp+var_2C]
0x1003aaa7  sub     eax, [ebp+var_1C]
0x1003aaaa  sub     eax, 4
0x1003aaad  push    ecx; Size
0x1003aaae  cmp     eax, ecx
0x1003aab0  jb      short loc_1003AB22
0x1003aab2  mov     ecx, [ebp+var_30]
0x1003aab5  mov     eax, [ebp+var_1C]
0x1003aab8  add     ecx, 4
0x1003aabb  add     eax, ecx
0x1003aabd  push    eax; Src
0x1003aabe  mov     eax, [ebp+arg_0]
0x1003aac1  mov     eax, [eax+4]
0x1003aac4  add     eax, esi
0x1003aac6  push    eax; void *
0x1003aac7  call    _memcpy
0x1003aacc  add     edi, [ebp+var_10]
0x1003aacf  add     esp, 0Ch
0x1003aad2  add     esi, [ebp+var_10]
0x1003aad5  mov     eax, [ebp+arg_0]
0x1003aad8  cmp     edi, [ebx+810h]
0x1003aade  jnb     short loc_1003AB0C
0x1003aae0  cmp     esi, [eax+8]
0x1003aae3  jnb     short loc_1003AB0C
0x1003aae5  mov     ecx, [ebp+var_18]
0x1003aae8  lea     eax, [ecx+7F0h]
0x1003aaee  cmp     edi, eax
0x1003aaf0  jb      short loc_1003AB09
0x1003aaf2  push    [ebp+arg_8]; struct Err *
0x1003aaf5  lea     eax, [ebp+var_20]
0x1003aaf8  push    eax; unsigned int *
0x1003aaf9  lea     eax, [ebp+var_40]
0x1003aafc  push    eax; struct DataPage *
0x1003aafd  push    edi; unsigned int
0x1003aafe  push    ecx; struct tagColParams *
0x1003aaff  mov     ecx, ebx; this
0x1003ab01  call    ?ReadDPOfOffset@LvDataOrig@@AAEKPAUtagColParams@@KAAVDataPage@@PAKAAVErr@@@Z; LvDataOrig::ReadDPOfOffset(tagColParams *,ulong,DataPage &,ulong *,Err &)
0x1003ab06  mov     [ebp+var_18], eax
0x1003ab09  mov     eax, [ebp+arg_0]
0x1003ab0c  mov     edx, [ebp+arg_8]
0x1003ab0f  test    byte ptr [edx], 8
0x1003ab12  jz      loc_1003A9E0
0x1003ab18  jmp     short loc_1003AB34
0x1003ab1a  push    ecx
0x1003ab1b  push    0FFFFFC07h
0x1003ab20  jmp     short loc_1003AB27
0x1003ab22  push    0FFFFF9B5h
0x1003ab27  mov     ecx, edx
0x1003ab29  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003ab2e  mov     edx, [ebp+arg_8]
0x1003ab31  mov     eax, [ebp+arg_0]
0x1003ab34  cmp     esi, [eax+8]
0x1003ab37  jnz     short loc_1003AB4D
0x1003ab39  cmp     edi, [ebx+810h]
0x1003ab3f  jz      short loc_1003AB4D
0x1003ab41  push    3EEh; int
0x1003ab46  mov     ecx, edx; this
0x1003ab48  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1003ab4d  mov     ecx, [ebp+var_40]
0x1003ab50  test    ecx, ecx
0x1003ab52  jz      short loc_1003AB58
0x1003ab54  dec     word ptr [ecx+4Ch]
0x1003ab58  mov     eax, esi
0x1003ab5a  mov     ecx, [ebp+var_C]
0x1003ab5d  mov     large fs:0, ecx
0x1003ab64  pop     ecx
0x1003ab65  pop     edi
0x1003ab66  pop     esi
0x1003ab67  pop     ebx
0x1003ab68  mov     esp, ebp
0x1003ab6a  pop     ebp
0x1003ab6b  retn    10h
0x10060e70  lea     ecx, [ebp+var_40]; this
0x10060e73  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
0x10060e7d  nop
0x10060e7e  nop
0x10060e7f  mov     edx, [esp-4+arg_4]
0x10060e83  lea     eax, [edx+0Ch]
0x10060e86  mov     ecx, [edx-44h]
0x10060e89  xor     ecx, eax; StackCookie
0x10060e8b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060e90  mov     eax, offset stru_10063A64
0x10060e95  jmp     ___CxxFrameHandler3
```
