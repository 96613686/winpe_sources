# CFontFolderData::_TotalFamilyFilePathSize(_ITEMIDLIST const *,ulong *)

- ea: `0x1800125f4`
- end: `0x180012713`
- name: `?_TotalFamilyFilePathSize@CFontFolderData@@AEAAJPEFBU_ITEMIDLIST@@PEAK@Z`
- size: `287`
- prototype: `__int64 __fastcall(CFontFolderData *this, const struct _ITEMIDLIST *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800123e8`

## callees

- `0x18001252c`
- `0x1800125f4`
- `0x180012d60`
- `0x1800225ac`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800126d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800126d4`

## pseudocode

```c
__int64 __fastcall CFontFolderData::_TotalFamilyFilePathSize(
        CFontFolderData *this,
        const struct _ITEMIDLIST *a2,
        unsigned int *a3)
{
  signed int v5; // ebx
  unsigned int v6; // edi
  CFontFolderData *v7; // rcx
  int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // edx
  unsigned int v12; // [rsp+30h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-21h] BYREF
  void *v14; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 v15[32]; // [rsp+50h] [rbp-9h] BYREF

  memset_0(v15, 0, sizeof(v15));
  v5 = FID_FamilyName(a2, v15, 0x20u);
  if ( v5 >= 0 )
  {
    v14 = 0;
    v5 = CFontFolderEnum::CreateInstance(v15, 0x40u, &GUID_000214f2_0000_0000_c000_000000000046, &v14);
    if ( v5 >= 0 )
    {
      v6 = 0;
      pv = 0;
      while ( !(*(unsigned int (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)v14 + 24LL))(v14, 1, &pv)
           && v5 >= 0 )
      {
        v12 = 0;
        v5 = CFontFolderData::_ItemFilePathSize(v7, (const struct _ITEMIDLIST *)pv, &v12);
        if ( v5 >= 0 )
        {
          v8 = -1;
          v9 = v6 + v12;
          v10 = v6;
          if ( v6 + v12 >= v6 )
            v8 = v6 + v12;
          v6 = v8;
          v5 = v9 < v10 ? 0x80070216 : 0;
        }
        if ( pv )
          CoTaskMemFree(pv);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v5 >= 0 )
        *a3 = v6;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800125f4  mov     [rsp-8+arg_0], rbx
0x1800125f9  push    rbp
0x1800125fa  push    rsi
0x1800125fb  push    rdi
0x1800125fc  lea     rbp, [rsp-47h]
0x180012601  sub     rsp, 0A0h
0x180012608  mov     rax, cs:__security_cookie
0x18001260f  xor     rax, rsp
0x180012612  mov     [rbp+57h+var_20], rax
0x180012616  mov     rsi, r8
0x180012619  lea     rcx, [rbp+57h+var_60]; void *
0x18001261d  mov     rbx, rdx
0x180012620  mov     edi, 40h ; '@'
0x180012625  mov     r8d, edi; Size
0x180012628  xor     edx, edx; Val
0x18001262a  call    memset_0
0x18001262f  lea     r8d, [rdi-20h]; unsigned __int64
0x180012633  mov     rcx, rbx; struct _ITEMIDLIST *
0x180012636  lea     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x18001263a  call    ?FID_FamilyName@@YAJPEFBU_ITEMIDLIST@@PEAG_K@Z; FID_FamilyName(_ITEMIDLIST const *,ushort *,unsigned __int64)
0x18001263f  mov     ebx, eax
0x180012641  test    eax, eax
0x180012643  js      loc_1800126F2
0x180012649  lea     r9, [rbp+57h+var_70]; void **
0x18001264d  mov     [rbp+57h+var_70], 0
0x180012655  lea     r8, _GUID_000214f2_0000_0000_c000_000000000046; struct _GUID *
0x18001265c  mov     edx, edi; unsigned int
0x18001265e  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x180012662  call    ?CreateInstance@CFontFolderEnum@@SAJPEBGKAEBU_GUID@@PEAPEAX@Z; CFontFolderEnum::CreateInstance(ushort const *,ulong,_GUID const &,void * *)
0x180012667  mov     ebx, eax
0x180012669  test    eax, eax
0x18001266b  js      loc_1800126F2
0x180012671  xor     edi, edi
0x180012673  mov     [rbp+57h+pv], rdi
0x180012677  mov     rcx, [rbp+57h+var_70]
0x18001267b  lea     r8, [rbp+57h+pv]
0x18001267f  xor     r9d, r9d
0x180012682  mov     rax, [rcx]
0x180012685  lea     edx, [r9+1]
0x180012689  mov     rax, [rax+18h]
0x18001268d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012692  test    eax, eax
0x180012694  jnz     short loc_1800126DC
0x180012696  test    ebx, ebx
0x180012698  js      short loc_1800126DC
0x18001269a  mov     rdx, [rbp+57h+pv]; struct _ITEMIDLIST *
0x18001269e  lea     r8, [rbp+57h+var_80]; unsigned int *
0x1800126a2  mov     [rbp+57h+var_80], eax
0x1800126a5  call    ?_ItemFilePathSize@CFontFolderData@@AEAAJPEFBU_ITEMIDLIST@@PEAK@Z; CFontFolderData::_ItemFilePathSize(_ITEMIDLIST const *,ulong *)
0x1800126aa  mov     ebx, eax
0x1800126ac  test    eax, eax
0x1800126ae  js      short loc_1800126CB
0x1800126b0  mov     ecx, [rbp+57h+var_80]
0x1800126b3  or      eax, 0FFFFFFFFh
0x1800126b6  add     ecx, edi
0x1800126b8  mov     edx, edi
0x1800126ba  cmp     ecx, edi
0x1800126bc  cmovnb  eax, ecx
0x1800126bf  cmp     ecx, edx
0x1800126c1  mov     edi, eax
0x1800126c3  sbb     ebx, ebx
0x1800126c5  and     ebx, 80070216h
0x1800126cb  mov     rcx, [rbp+57h+pv]; pv
0x1800126cf  test    rcx, rcx
0x1800126d2  jz      short loc_180012677
0x1800126d4  call    cs:__imp_CoTaskMemFree
0x1800126da  jmp     short loc_180012677
0x1800126dc  mov     rcx, [rbp+57h+var_70]
0x1800126e0  mov     rax, [rcx]
0x1800126e3  mov     rax, [rax+10h]
0x1800126e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126ec  test    ebx, ebx
0x1800126ee  js      short loc_1800126F2
0x1800126f0  mov     [rsi], edi
0x1800126f2  mov     eax, ebx
0x1800126f4  mov     rcx, [rbp+57h+var_20]
0x1800126f8  xor     rcx, rsp; StackCookie
0x1800126fb  call    __security_check_cookie
0x180012700  mov     rbx, [rsp+0B0h+arg_0]
0x180012708  add     rsp, 0A0h
0x18001270f  pop     rdi
0x180012710  pop     rsi
0x180012711  pop     rbp
0x180012712  retn
```
