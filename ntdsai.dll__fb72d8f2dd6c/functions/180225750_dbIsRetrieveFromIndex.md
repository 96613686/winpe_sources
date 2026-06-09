# dbIsRetrieveFromIndex

- ea: `0x180225750`
- end: `0x180225a23`
- name: `dbIsRetrieveFromIndex`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180224250`

## callees

- `0x18019ddb0`
- `0x18019e3d0`
- `0x180225750`
- `0x180453394`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180225796`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1802257af`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1802257c8`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1802257e1`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1802257fa`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180225818`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180225831`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180225796`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1802257af`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1802257c8`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1802257e1`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1802257fa`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180225818`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180225831`

## string_xrefs

- `0x18022578c`: `link_present_active_index`
- `0x1802257a5`: `link_present_index`
- `0x180225917`: `link_del_index`
- `0x1802258fb`: `link_USN_index`
- `0x18022597b`: `link_USN_index`
- `0x18022592e`: `link_expiration_time_index`
- `0x1802257be`: `link_legacy_index`
- `0x180225888`: `link_attr_USN_index`
- `0x180225852`: `link_DRA_USN_index`
- `0x180225945`: `link_DRA_USN_index`
- `0x18022599b`: `link_DRA_USN_index`
- `0x1802257d7`: `link_base_and_data_index`
- `0x18022580e`: `link_base_and_data_index`
- `0x18022589f`: `link_base_and_data_index`
- `0x1802259c5`: `link_base_and_data_index`
- `0x1802258b6`: `link_base_and_data_v2_index`
- `0x1802259eb`: `link_base_and_data_v2_index`
- `0x180225827`: `link_bdnt_and_base_and_data_index`
- `0x1802259d8`: `link_bdnt_and_base_and_data_index`
- `0x1802259fe`: `link_bdnt_and_base_and_data_v2_index`
- `0x180225871`: `link_dirsync2_index`
- `0x180225964`: `link_dirsync2_index`
- `0x1802259b2`: `link_dirsync2_index`
- `0x1802257f0`: `link_dnt_and_base_and_data_index`
- `0x1802258cd`: `link_dnt_and_base_and_data_index`
- `0x1802258e4`: `link_dnt_and_base_and_data_v2_index`

## pseudocode

```c
_BOOL8 __fastcall dbIsRetrieveFromIndex(int a1, const char *a2)
{
  int v4; // ebp

  if ( (a1 & 1) == 0 )
  {
    v4 = DBIsDirsyncSetIndexName(a2);
    if ( (unsigned int)DBIsLinkSegmentIndexName(a2) )
    {
      if ( (!__CFSHR__(a1, 2)
         || !strstr(a2, "link_present_active_index")
         && !strstr(a2, "link_present_index")
         && !strstr(a2, "link_legacy_index")
         && !strstr(a2, "link_base_and_data_index")
         && !strstr(a2, "link_dnt_and_base_and_data_index"))
        && ((a1 & 8) == 0 || !strstr(a2, "link_base_and_data_index") && !strstr(a2, "link_bdnt_and_base_and_data_index")) )
      {
        return 1;
      }
    }
    else if ( (!__CFSHR__(a1, 2)
            || strcmp_0(a2, "link_DRA_USN_index")
            && !v4
            && strcmp_0(a2, "link_dirsync2_index")
            && strcmp_0(a2, "link_attr_USN_index")
            && strcmp_0(a2, "link_base_and_data_index")
            && strcmp_0(a2, "link_base_and_data_v2_index")
            && strcmp_0(a2, "link_dnt_and_base_and_data_index")
            && strcmp_0(a2, "link_dnt_and_base_and_data_v2_index")
            && strcmp_0(a2, "link_USN_index"))
           && ((a1 & 4) == 0
            || strcmp_0(a2, "link_del_index")
            && strcmp_0(a2, "link_expiration_time_index")
            && strcmp_0(a2, "link_DRA_USN_index")
            && !v4
            && strcmp_0(a2, "link_dirsync2_index")
            && strcmp_0(a2, "link_USN_index")) )
    {
      if ( (a1 & 8) == 0 )
        return 1;
      if ( strcmp_0(a2, "link_DRA_USN_index")
        && !v4
        && strcmp_0(a2, "link_dirsync2_index")
        && strcmp_0(a2, "link_base_and_data_index")
        && strcmp_0(a2, "link_bdnt_and_base_and_data_index")
        && strcmp_0(a2, "link_base_and_data_v2_index") )
      {
        return strcmp_0(a2, "link_bdnt_and_base_and_data_v2_index") != 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180225750  push    rbx
0x180225752  push    rbp
0x180225753  push    rsi
0x180225754  push    rdi
0x180225755  sub     rsp, 28h
0x180225759  mov     rdi, rdx
0x18022575c  mov     ebx, ecx
0x18022575e  test    cl, 1
0x180225761  jnz     loc_180225A18
0x180225767  mov     rcx, rdx
0x18022576a  call    DBIsDirsyncSetIndexName
0x18022576f  mov     esi, ebx
0x180225771  mov     rcx, rdi
0x180225774  shr     esi, 2
0x180225777  mov     ebp, eax
0x180225779  sbb     esi, esi
0x18022577b  call    DBIsLinkSegmentIndexName
0x180225780  test    eax, eax
0x180225782  jz      loc_18022584A
0x180225788  test    esi, esi
0x18022578a  jz      short loc_180225809
0x18022578c  lea     rdx, aLinkPresentAct; "link_present_active_index"
0x180225793  mov     rcx, rdi; Str
0x180225796  call    cs:__imp_strstr
0x18022579c  test    rax, rax
0x18022579f  jnz     loc_180225A18
0x1802257a5  lea     rdx, aLinkPresentInd; "link_present_index"
0x1802257ac  mov     rcx, rdi; Str
0x1802257af  call    cs:__imp_strstr
0x1802257b5  test    rax, rax
0x1802257b8  jnz     loc_180225A18
0x1802257be  lea     rdx, aLinkLegacyInde; "link_legacy_index"
0x1802257c5  mov     rcx, rdi; Str
0x1802257c8  call    cs:__imp_strstr
0x1802257ce  test    rax, rax
0x1802257d1  jnz     loc_180225A18
0x1802257d7  lea     rdx, aLinkBaseAndDat; "link_base_and_data_index"
0x1802257de  mov     rcx, rdi; Str
0x1802257e1  call    cs:__imp_strstr
0x1802257e7  test    rax, rax
0x1802257ea  jnz     loc_180225A18
0x1802257f0  lea     rdx, aLinkDntAndBase_0; "link_dnt_and_base_and_data_index"
0x1802257f7  mov     rcx, rdi; Str
0x1802257fa  call    cs:__imp_strstr
0x180225800  test    rax, rax
0x180225803  jnz     loc_180225A18
0x180225809  test    bl, 8
0x18022580c  jz      short loc_180225840
0x18022580e  lea     rdx, aLinkBaseAndDat; "link_base_and_data_index"
0x180225815  mov     rcx, rdi; Str
0x180225818  call    cs:__imp_strstr
0x18022581e  test    rax, rax
0x180225821  jnz     loc_180225A18
0x180225827  lea     rdx, aLinkBdntAndBas; "link_bdnt_and_base_and_data_index"
0x18022582e  mov     rcx, rdi; Str
0x180225831  call    cs:__imp_strstr
0x180225837  test    rax, rax
0x18022583a  jnz     loc_180225A18
0x180225840  mov     eax, 1
0x180225845  jmp     loc_180225A1A
0x18022584a  test    esi, esi
0x18022584c  jz      loc_180225912
0x180225852  lea     rdx, aLinkDraUsnInde; "link_DRA_USN_index"
0x180225859  mov     rcx, rdi; Str1
0x18022585c  call    strcmp_0
0x180225861  test    eax, eax
0x180225863  jz      loc_180225A18
0x180225869  test    ebp, ebp
0x18022586b  jnz     loc_180225A18
0x180225871  lea     rdx, aLinkDirsync2In; "link_dirsync2_index"
0x180225878  mov     rcx, rdi; Str1
0x18022587b  call    strcmp_0
0x180225880  test    eax, eax
0x180225882  jz      loc_180225A18
0x180225888  lea     rdx, aLinkAttrUsnInd; "link_attr_USN_index"
0x18022588f  mov     rcx, rdi; Str1
0x180225892  call    strcmp_0
0x180225897  test    eax, eax
0x180225899  jz      loc_180225A18
0x18022589f  lea     rdx, aLinkBaseAndDat; "link_base_and_data_index"
0x1802258a6  mov     rcx, rdi; Str1
0x1802258a9  call    strcmp_0
0x1802258ae  test    eax, eax
0x1802258b0  jz      loc_180225A18
0x1802258b6  lea     rdx, aLinkBaseAndDat_0; "link_base_and_data_v2_index"
0x1802258bd  mov     rcx, rdi; Str1
0x1802258c0  call    strcmp_0
0x1802258c5  test    eax, eax
0x1802258c7  jz      loc_180225A18
0x1802258cd  lea     rdx, aLinkDntAndBase_0; "link_dnt_and_base_and_data_index"
0x1802258d4  mov     rcx, rdi; Str1
0x1802258d7  call    strcmp_0
0x1802258dc  test    eax, eax
0x1802258de  jz      loc_180225A18
0x1802258e4  lea     rdx, aLinkDntAndBase; "link_dnt_and_base_and_data_v2_index"
0x1802258eb  mov     rcx, rdi; Str1
0x1802258ee  call    strcmp_0
0x1802258f3  test    eax, eax
0x1802258f5  jz      loc_180225A18
0x1802258fb  lea     rdx, aLinkUsnIndex; "link_USN_index"
0x180225902  mov     rcx, rdi; Str1
0x180225905  call    strcmp_0
0x18022590a  test    eax, eax
0x18022590c  jz      loc_180225A18
0x180225912  test    bl, 4
0x180225915  jz      short loc_180225992
0x180225917  lea     rdx, aLinkDelIndex; "link_del_index"
0x18022591e  mov     rcx, rdi; Str1
0x180225921  call    strcmp_0
0x180225926  test    eax, eax
0x180225928  jz      loc_180225A18
0x18022592e  lea     rdx, aLinkExpiration; "link_expiration_time_index"
0x180225935  mov     rcx, rdi; Str1
0x180225938  call    strcmp_0
0x18022593d  test    eax, eax
0x18022593f  jz      loc_180225A18
0x180225945  lea     rdx, aLinkDraUsnInde; "link_DRA_USN_index"
0x18022594c  mov     rcx, rdi; Str1
0x18022594f  call    strcmp_0
0x180225954  test    eax, eax
0x180225956  jz      loc_180225A18
0x18022595c  test    ebp, ebp
0x18022595e  jnz     loc_180225A18
0x180225964  lea     rdx, aLinkDirsync2In; "link_dirsync2_index"
0x18022596b  mov     rcx, rdi; Str1
0x18022596e  call    strcmp_0
0x180225973  test    eax, eax
0x180225975  jz      loc_180225A18
0x18022597b  lea     rdx, aLinkUsnIndex; "link_USN_index"
0x180225982  mov     rcx, rdi; Str1
0x180225985  call    strcmp_0
0x18022598a  test    eax, eax
0x18022598c  jz      loc_180225A18
0x180225992  test    bl, 8
0x180225995  jz      loc_180225840
0x18022599b  lea     rdx, aLinkDraUsnInde; "link_DRA_USN_index"
0x1802259a2  mov     rcx, rdi; Str1
0x1802259a5  call    strcmp_0
0x1802259aa  test    eax, eax
0x1802259ac  jz      short loc_180225A18
0x1802259ae  test    ebp, ebp
0x1802259b0  jnz     short loc_180225A18
0x1802259b2  lea     rdx, aLinkDirsync2In; "link_dirsync2_index"
0x1802259b9  mov     rcx, rdi; Str1
0x1802259bc  call    strcmp_0
0x1802259c1  test    eax, eax
0x1802259c3  jz      short loc_180225A18
0x1802259c5  lea     rdx, aLinkBaseAndDat; "link_base_and_data_index"
0x1802259cc  mov     rcx, rdi; Str1
0x1802259cf  call    strcmp_0
0x1802259d4  test    eax, eax
0x1802259d6  jz      short loc_180225A18
0x1802259d8  lea     rdx, aLinkBdntAndBas; "link_bdnt_and_base_and_data_index"
0x1802259df  mov     rcx, rdi; Str1
0x1802259e2  call    strcmp_0
0x1802259e7  test    eax, eax
0x1802259e9  jz      short loc_180225A18
0x1802259eb  lea     rdx, aLinkBaseAndDat_0; "link_base_and_data_v2_index"
0x1802259f2  mov     rcx, rdi; Str1
0x1802259f5  call    strcmp_0
0x1802259fa  test    eax, eax
0x1802259fc  jz      short loc_180225A18
0x1802259fe  lea     rdx, aLinkBdntAndBas_0; "link_bdnt_and_base_and_data_v2_index"
0x180225a05  mov     rcx, rdi; Str1
0x180225a08  call    strcmp_0
0x180225a0d  xor     ecx, ecx
0x180225a0f  test    eax, eax
0x180225a11  setnz   cl
0x180225a14  mov     eax, ecx
0x180225a16  jmp     short loc_180225A1A
0x180225a18  xor     eax, eax
0x180225a1a  add     rsp, 28h
0x180225a1e  pop     rdi
0x180225a1f  pop     rsi
0x180225a20  pop     rbp
0x180225a21  pop     rbx
0x180225a22  retn
```
