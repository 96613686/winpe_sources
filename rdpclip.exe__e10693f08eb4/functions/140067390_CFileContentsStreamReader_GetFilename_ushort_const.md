# CFileContentsStreamReader::GetFilename(ushort const * *)

- ea: `0x140067390`
- end: `0x140067656`
- name: `?GetFilename@CFileContentsStreamReader@@UEAAJPEAPEBG@Z`
- size: `710`
- prototype: `__int64 __fastcall(CFileContentsStreamReader *__hidden this, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005750`
- `0x140008c9c`
- `0x140011054`
- `0x1400186e4`
- `0x1400188b0`
- `0x140067390`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006761e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006761e`

## string_xrefs

- `0x14006745f`: `m_spCachedStream`
- `0x1400675ec`: `StringCchCopy failed.`

## pseudocode

```c
__int64 __fastcall CFileContentsStreamReader::GetFilename(CFileContentsStreamReader *this, unsigned __int16 **a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  int v7; // ebx
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  unsigned __int64 v11; // rbx
  size_t v12; // rsi
  unsigned __int16 *v13; // rax
  unsigned int v14; // eax
  unsigned __int64 v16; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int16 *v17[10]; // [rsp+40h] [rbp-68h] BYREF

  memset_0(v17, 0, sizeof(v17));
  v16 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 53;
    v6 = "ppszFilename";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)&WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v6);
LABEL_7:
    v7 = -2147467261;
    goto LABEL_35;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 54;
    v6 = "m_spCachedStream";
    goto LABEL_6;
  }
  *a2 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **, __int64))(**((_QWORD **)this + 4) + 96LL))(
         *((_QWORD *)this + 4),
         v17,
         1);
  if ( v7 >= 0 )
  {
    v7 = StringCchLengthW(v17[0], 0x104u, &v16);
    if ( v7 >= 0 )
    {
      v11 = v16;
      v12 = 2 * v16 + 2;
      v13 = (unsigned __int16 *)PAL_System_MemAlloc(v12);
      *a2 = v13;
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            (unsigned int)&WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids,
            v14,
            (__int64)"PCWSTR");
        }
        v7 = -2147024882;
        goto LABEL_35;
      }
      memset_0(v13, 0, v12);
      v7 = StringCchCopyW(*a2, v11 + 1, v17[0]);
      if ( v7 >= 0 )
        return 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 58;
        v10 = "StringCchCopy failed.";
        goto LABEL_34;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 56;
      v10 = "StringCchLength failed.";
      goto LABEL_34;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 55;
    v10 = "Stat failed.";
LABEL_34:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)&WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids,
      v8,
      (__int64)v10,
      v7);
  }
LABEL_35:
  if ( *a2 )
  {
    LocalFree(*a2);
    *a2 = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140067390  mov     [rsp+arg_10], rbx
0x140067395  mov     [rsp+arg_18], rsi
0x14006739a  push    rdi
0x14006739b  sub     rsp, 0A0h
0x1400673a2  mov     rax, cs:__security_cookie
0x1400673a9  xor     rax, rsp
0x1400673ac  mov     [rsp+0A8h+var_18], rax
0x1400673b4  mov     rdi, rdx
0x1400673b7  mov     rbx, rcx
0x1400673ba  xor     edx, edx; Val
0x1400673bc  lea     rcx, [rsp+0A8h+var_68]; void *
0x1400673c1  lea     r8d, [rdx+50h]; Size
0x1400673c5  call    memset_0
0x1400673ca  mov     [rsp+0A8h+var_78], 0
0x1400673d3  test    rdi, rdi
0x1400673d6  jnz     short loc_14006742F
0x1400673d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400673df  lea     rax, WPP_GLOBAL_Control
0x1400673e6  cmp     rcx, rax
0x1400673e9  jz      short loc_140067425
0x1400673eb  test    byte ptr [rcx+1Ch], 8
0x1400673ef  jz      short loc_140067425
0x1400673f1  cmp     byte ptr [rcx+19h], 2
0x1400673f5  jb      short loc_140067425
0x1400673f7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400673fc  lea     edx, [rdi+35h]
0x1400673ff  lea     rcx, aPpszfilename; "ppszFilename"
0x140067406  mov     [rsp+0A8h+var_88], rcx
0x14006740b  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x140067412  mov     rcx, cs:WPP_GLOBAL_Control
0x140067419  mov     r9d, eax
0x14006741c  mov     rcx, [rcx+10h]
0x140067420  call    WPP_SF_Ds
0x140067425  mov     ebx, 80004003h
0x14006742a  jmp     loc_140067616
0x14006742f  cmp     qword ptr [rbx+20h], 0
0x140067434  jnz     short loc_140067468
0x140067436  mov     rcx, cs:WPP_GLOBAL_Control
0x14006743d  lea     rax, WPP_GLOBAL_Control
0x140067444  cmp     rcx, rax
0x140067447  jz      short loc_140067425
0x140067449  test    byte ptr [rcx+1Ch], 8
0x14006744d  jz      short loc_140067425
0x14006744f  cmp     byte ptr [rcx+19h], 2
0x140067453  jb      short loc_140067425
0x140067455  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006745a  mov     edx, 36h ; '6'
0x14006745f  lea     rcx, aMSpcachedstrea; "m_spCachedStream"
0x140067466  jmp     short loc_140067406
0x140067468  mov     qword ptr [rdi], 0
0x14006746f  lea     rdx, [rsp+0A8h+var_68]
0x140067474  mov     rcx, [rbx+20h]
0x140067478  mov     r8d, 1
0x14006747e  mov     rax, [rcx]
0x140067481  mov     rax, [rax+60h]
0x140067485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006748a  mov     ebx, eax
0x14006748c  test    eax, eax
0x14006748e  jns     short loc_1400674D1
0x140067490  mov     rcx, cs:WPP_GLOBAL_Control
0x140067497  lea     rax, WPP_GLOBAL_Control
0x14006749e  cmp     rcx, rax
0x1400674a1  jz      loc_140067616
0x1400674a7  test    byte ptr [rcx+1Ch], 8
0x1400674ab  jz      loc_140067616
0x1400674b1  cmp     byte ptr [rcx+19h], 2
0x1400674b5  jb      loc_140067616
0x1400674bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400674c0  mov     edx, 37h ; '7'
0x1400674c5  lea     rcx, aStatFailed; "Stat failed."
0x1400674cc  jmp     loc_1400675F3
0x1400674d1  mov     rcx, [rsp+0A8h+var_68]; unsigned __int16 *
0x1400674d6  lea     r8, [rsp+0A8h+var_78]; unsigned __int64 *
0x1400674db  mov     edx, 104h; unsigned __int64
0x1400674e0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400674e5  mov     ebx, eax
0x1400674e7  test    eax, eax
0x1400674e9  jns     short loc_14006752C
0x1400674eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400674f2  lea     rax, WPP_GLOBAL_Control
0x1400674f9  cmp     rcx, rax
0x1400674fc  jz      loc_140067616
0x140067502  test    byte ptr [rcx+1Ch], 8
0x140067506  jz      loc_140067616
0x14006750c  cmp     byte ptr [rcx+19h], 2
0x140067510  jb      loc_140067616
0x140067516  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006751b  mov     edx, 38h ; '8'
0x140067520  lea     rcx, aStringcchlengt_0; "StringCchLength failed."
0x140067527  jmp     loc_1400675F3
0x14006752c  mov     rbx, [rsp+0A8h+var_78]
0x140067531  lea     rsi, ds:2[rbx*2]
0x140067539  mov     rcx, rsi
0x14006753c  call    PAL_System_MemAlloc
0x140067541  mov     [rdi], rax
0x140067544  test    rax, rax
0x140067547  jnz     short loc_14006759F
0x140067549  mov     rcx, cs:WPP_GLOBAL_Control
0x140067550  lea     rax, WPP_GLOBAL_Control
0x140067557  cmp     rcx, rax
0x14006755a  jz      short loc_140067598
0x14006755c  test    byte ptr [rcx+1Ch], 8
0x140067560  jz      short loc_140067598
0x140067562  cmp     byte ptr [rcx+19h], 2
0x140067566  jb      short loc_140067598
0x140067568  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006756d  lea     rcx, aPcwstr; "PCWSTR"
0x140067574  mov     edx, 39h ; '9'
0x140067579  mov     [rsp+0A8h+var_88], rcx
0x14006757e  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x140067585  mov     rcx, cs:WPP_GLOBAL_Control
0x14006758c  mov     r9d, eax
0x14006758f  mov     rcx, [rcx+10h]
0x140067593  call    WPP_SF_Ds
0x140067598  mov     ebx, 8007000Eh
0x14006759d  jmp     short loc_140067616
0x14006759f  mov     r8, rsi; Size
0x1400675a2  xor     edx, edx; Val
0x1400675a4  mov     rcx, rax; void *
0x1400675a7  call    memset_0
0x1400675ac  mov     r8, [rsp+0A8h+var_68]; unsigned __int16 *
0x1400675b1  lea     rdx, [rbx+1]; unsigned __int64
0x1400675b5  mov     rcx, [rdi]; unsigned __int16 *
0x1400675b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400675bd  mov     ebx, eax
0x1400675bf  test    eax, eax
0x1400675c1  jns     short loc_14006762D
0x1400675c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400675ca  lea     rax, WPP_GLOBAL_Control
0x1400675d1  cmp     rcx, rax
0x1400675d4  jz      short loc_140067616
0x1400675d6  test    byte ptr [rcx+1Ch], 8
0x1400675da  jz      short loc_140067616
0x1400675dc  cmp     byte ptr [rcx+19h], 2
0x1400675e0  jb      short loc_140067616
0x1400675e2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400675e7  mov     edx, 3Ah ; ':'
0x1400675ec  lea     rcx, aStringcchcopyF_2; "StringCchCopy failed."
0x1400675f3  mov     [rsp+0A8h+var_80], ebx
0x1400675f7  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x1400675fe  mov     [rsp+0A8h+var_88], rcx
0x140067603  mov     r9d, eax
0x140067606  mov     rcx, cs:WPP_GLOBAL_Control
0x14006760d  mov     rcx, [rcx+10h]
0x140067611  call    WPP_SF_DsD
0x140067616  mov     rcx, [rdi]; hMem
0x140067619  test    rcx, rcx
0x14006761c  jz      short loc_14006762F
0x14006761e  call    cs:__imp_LocalFree
0x140067624  mov     qword ptr [rdi], 0
0x14006762b  jmp     short loc_14006762F
0x14006762d  xor     ebx, ebx
0x14006762f  mov     eax, ebx
0x140067631  mov     rcx, [rsp+0A8h+var_18]
0x140067639  xor     rcx, rsp; StackCookie
0x14006763c  call    __security_check_cookie
0x140067641  lea     r11, [rsp+0A8h+var_8]
0x140067649  mov     rbx, [r11+20h]
0x14006764d  mov     rsi, [r11+28h]
0x140067651  mov     rsp, r11
0x140067654  pop     rdi
0x140067655  retn
```
