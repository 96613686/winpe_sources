# FILTERING_RULE::Create(INativeConfigurationElement *)

- ea: `0x180005050`
- end: `0x1800052d4`
- name: `?Create@FILTERING_RULE@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `644`
- prototype: `__int64 __fastcall(FILTERING_RULE *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003080`

## callees

- `0x180005050`
- `0x1800077f8`
- `0x180007988`
- `0x180008010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800050a8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800050a8`

## string_xrefs

- `0x180005229`: `fileExtension`

## pseudocode

```c
__int64 __fastcall FILTERING_RULE::Create(FILTERING_RULE *this, struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v5)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD); // rax
  int CollectionToMultisz; // ebx
  const unsigned __int16 *v8; // rdx
  int v9; // r9d
  int v10; // r9d
  int v11; // r9d
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF
  struct INativeConfigurationElementCollection *v13; // [rsp+60h] [rbp+18h] BYREF
  const unsigned __int16 *v14; // [rsp+68h] [rbp+20h] BYREF

  v2 = *(_QWORD *)a2;
  v12 = 0;
  v13 = 0;
  v5 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v2 + 64);
  v14 = 0;
  CollectionToMultisz = v5(a2, L"name", &v14, 0, 0);
  if ( CollectionToMultisz >= 0 )
  {
    CollectionToMultisz = STRU::Copy(this, v14);
    if ( CollectionToMultisz >= 0 )
    {
      CollectionToMultisz = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
                              a2,
                              L"scanUrl",
                              (char *)this + 56,
                              0,
                              0);
      if ( CollectionToMultisz >= 0 )
      {
        CollectionToMultisz = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
                                a2,
                                L"scanQueryString",
                                (char *)this + 60,
                                0,
                                0);
        if ( CollectionToMultisz >= 0 )
        {
          CollectionToMultisz = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
                                  a2,
                                  L"scanAllRaw",
                                  (char *)this + 64,
                                  0,
                                  0);
          if ( CollectionToMultisz >= 0 )
          {
            CollectionToMultisz = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
                                    a2,
                                    L"denyUnescapedPercent",
                                    (char *)this + 68,
                                    0,
                                    0);
            if ( CollectionToMultisz >= 0 )
            {
              CollectionToMultisz = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 32LL))(
                                      a2,
                                      L"scanHeaders",
                                      &v12);
              if ( CollectionToMultisz >= 0 )
              {
                CollectionToMultisz = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElementCollection **))(*(_QWORD *)v12 + 40LL))(
                                        v12,
                                        &v13);
                if ( CollectionToMultisz >= 0 )
                {
                  CollectionToMultisz = ReadCollectionToMultisz(v13, v8, (FILTERING_RULE *)((char *)this + 72), v9);
                  if ( CollectionToMultisz >= 0 )
                  {
                    CollectionToMultisz = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 32LL))(
                                            a2,
                                            L"appliesTo",
                                            &v12);
                    if ( CollectionToMultisz >= 0 )
                    {
                      CollectionToMultisz = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElementCollection **))(*(_QWORD *)v12 + 40LL))(
                                              v12,
                                              &v13);
                      if ( CollectionToMultisz >= 0 )
                      {
                        CollectionToMultisz = ReadCollectionToMultisz(
                                                v13,
                                                L"fileExtension",
                                                (FILTERING_RULE *)((char *)this + 128),
                                                v10);
                        if ( CollectionToMultisz >= 0 )
                        {
                          CollectionToMultisz = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 32LL))(
                                                  a2,
                                                  L"denyStrings",
                                                  &v12);
                          if ( CollectionToMultisz >= 0 )
                          {
                            CollectionToMultisz = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElementCollection **))(*(_QWORD *)v12 + 40LL))(
                                                    v12,
                                                    &v13);
                            if ( CollectionToMultisz >= 0 )
                            {
                              CollectionToMultisz = ReadCollectionToMultisz(
                                                      v13,
                                                      L"string",
                                                      (FILTERING_RULE *)((char *)this + 184),
                                                      v11);
                              if ( CollectionToMultisz >= 0 )
                                return 0;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
    (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)CollectionToMultisz;
}

```

## disassembly

```asm
0x180005050  mov     [rsp+arg_0], rbx
0x180005055  push    rbp
0x180005056  push    rsi
0x180005057  push    rdi
0x180005058  sub     rsp, 30h
0x18000505c  mov     rax, [rdx]
0x18000505f  lea     r8, [rsp+48h+arg_18]
0x180005064  xor     ebp, ebp
0x180005066  mov     rdi, rdx
0x180005069  mov     rsi, rcx
0x18000506c  mov     [rsp+48h+arg_8], rbp
0x180005071  xor     r9d, r9d
0x180005074  mov     [rsp+48h+arg_10], rbp
0x180005079  mov     rax, [rax+40h]
0x18000507d  lea     rdx, aName; "name"
0x180005084  mov     rcx, rdi
0x180005087  mov     [rsp+48h+arg_18], rbp
0x18000508c  mov     [rsp+48h+var_28], rbp
0x180005091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005096  mov     ebx, eax
0x180005098  test    eax, eax
0x18000509a  js      loc_18000512C
0x1800050a0  mov     rdx, [rsp+48h+arg_18]
0x1800050a5  mov     rcx, rsi
0x1800050a8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800050ae  mov     ebx, eax
0x1800050b0  test    eax, eax
0x1800050b2  js      short loc_18000512C
0x1800050b4  mov     rax, [rdi]
0x1800050b7  lea     r8, [rsi+38h]
0x1800050bb  xor     r9d, r9d
0x1800050be  mov     [rsp+48h+var_28], rbp
0x1800050c3  lea     rdx, aScanurl; "scanUrl"
0x1800050ca  mov     rcx, rdi
0x1800050cd  mov     rax, [rax+48h]
0x1800050d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d6  mov     ebx, eax
0x1800050d8  test    eax, eax
0x1800050da  js      short loc_18000512C
0x1800050dc  mov     rax, [rdi]
0x1800050df  lea     r8, [rsi+3Ch]
0x1800050e3  xor     r9d, r9d
0x1800050e6  mov     [rsp+48h+var_28], rbp
0x1800050eb  lea     rdx, aScanquerystrin; "scanQueryString"
0x1800050f2  mov     rcx, rdi
0x1800050f5  mov     rax, [rax+48h]
0x1800050f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050fe  mov     ebx, eax
0x180005100  test    eax, eax
0x180005102  js      short loc_18000512C
0x180005104  mov     rax, [rdi]
0x180005107  lea     r8, [rsi+40h]
0x18000510b  xor     r9d, r9d
0x18000510e  mov     [rsp+48h+var_28], rbp
0x180005113  lea     rdx, aScanallraw; "scanAllRaw"
0x18000511a  mov     rcx, rdi
0x18000511d  mov     rax, [rax+48h]
0x180005121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005126  mov     ebx, eax
0x180005128  test    eax, eax
0x18000512a  jns     short loc_180005157
0x18000512c  mov     rcx, [rsp+48h+arg_8]
0x180005131  test    rcx, rcx
0x180005134  jnz     loc_1800052AD
0x18000513a  mov     rcx, [rsp+48h+arg_10]
0x18000513f  test    rcx, rcx
0x180005142  jnz     loc_1800052C3
0x180005148  mov     eax, ebx
0x18000514a  mov     rbx, [rsp+48h+arg_0]
0x18000514f  add     rsp, 30h
0x180005153  pop     rdi
0x180005154  pop     rsi
0x180005155  pop     rbp
0x180005156  retn
0x180005157  mov     rax, [rdi]
0x18000515a  lea     r8, [rsi+44h]
0x18000515e  xor     r9d, r9d
0x180005161  mov     [rsp+48h+var_28], rbp
0x180005166  lea     rdx, aDenyunescapedp; "denyUnescapedPercent"
0x18000516d  mov     rcx, rdi
0x180005170  mov     rax, [rax+48h]
0x180005174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005179  mov     ebx, eax
0x18000517b  test    eax, eax
0x18000517d  js      short loc_18000512C
0x18000517f  mov     rax, [rdi]
0x180005182  lea     r8, [rsp+48h+arg_8]
0x180005187  lea     rdx, aScanheaders; "scanHeaders"
0x18000518e  mov     rcx, rdi
0x180005191  mov     rax, [rax+20h]
0x180005195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000519a  mov     ebx, eax
0x18000519c  test    eax, eax
0x18000519e  js      short loc_18000512C
0x1800051a0  mov     rcx, [rsp+48h+arg_8]
0x1800051a5  lea     rdx, [rsp+48h+arg_10]
0x1800051aa  mov     rax, [rcx]
0x1800051ad  mov     rax, [rax+28h]
0x1800051b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b6  mov     ebx, eax
0x1800051b8  test    eax, eax
0x1800051ba  js      loc_18000512C
0x1800051c0  mov     rcx, [rsp+48h+arg_10]; struct INativeConfigurationElementCollection *
0x1800051c5  lea     r8, [rsi+48h]; struct MULTISZA *
0x1800051c9  call    ?ReadCollectionToMultisz@@YAJPEAVINativeConfigurationElementCollection@@PEBGPEAVMULTISZA@@H@Z; ReadCollectionToMultisz(INativeConfigurationElementCollection *,ushort const *,MULTISZA *,int)
0x1800051ce  mov     ebx, eax
0x1800051d0  test    eax, eax
0x1800051d2  js      loc_18000512C
0x1800051d8  mov     rax, [rdi]
0x1800051db  lea     r8, [rsp+48h+arg_8]
0x1800051e0  lea     rdx, aAppliesto; "appliesTo"
0x1800051e7  mov     rcx, rdi
0x1800051ea  mov     rax, [rax+20h]
0x1800051ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f3  mov     ebx, eax
0x1800051f5  test    eax, eax
0x1800051f7  js      loc_18000512C
0x1800051fd  mov     rcx, [rsp+48h+arg_8]
0x180005202  lea     rdx, [rsp+48h+arg_10]
0x180005207  mov     rax, [rcx]
0x18000520a  mov     rax, [rax+28h]
0x18000520e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005213  mov     ebx, eax
0x180005215  test    eax, eax
0x180005217  js      loc_18000512C
0x18000521d  mov     rcx, [rsp+48h+arg_10]; struct INativeConfigurationElementCollection *
0x180005222  lea     r8, [rsi+80h]; struct MULTISZ *
0x180005229  lea     rdx, aFileextension; "fileExtension"
0x180005230  call    ?ReadCollectionToMultisz@@YAJPEAVINativeConfigurationElementCollection@@PEBGPEAVMULTISZ@@H@Z; ReadCollectionToMultisz(INativeConfigurationElementCollection *,ushort const *,MULTISZ *,int)
0x180005235  mov     ebx, eax
0x180005237  test    eax, eax
0x180005239  js      loc_18000512C
0x18000523f  mov     rax, [rdi]
0x180005242  lea     r8, [rsp+48h+arg_8]
0x180005247  lea     rdx, aDenystrings; "denyStrings"
0x18000524e  mov     rcx, rdi
0x180005251  mov     rax, [rax+20h]
0x180005255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000525a  mov     ebx, eax
0x18000525c  test    eax, eax
0x18000525e  js      loc_18000512C
0x180005264  mov     rcx, [rsp+48h+arg_8]
0x180005269  lea     rdx, [rsp+48h+arg_10]
0x18000526e  mov     rax, [rcx]
0x180005271  mov     rax, [rax+28h]
0x180005275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000527a  mov     ebx, eax
0x18000527c  test    eax, eax
0x18000527e  js      loc_18000512C
0x180005284  mov     rcx, [rsp+48h+arg_10]; struct INativeConfigurationElementCollection *
0x180005289  lea     r8, [rsi+0B8h]; struct MULTISZ *
0x180005290  lea     rdx, aString; "string"
0x180005297  call    ?ReadCollectionToMultisz@@YAJPEAVINativeConfigurationElementCollection@@PEBGPEAVMULTISZ@@H@Z; ReadCollectionToMultisz(INativeConfigurationElementCollection *,ushort const *,MULTISZ *,int)
0x18000529c  mov     ebx, eax
0x18000529e  test    eax, eax
0x1800052a0  js      loc_18000512C
0x1800052a6  xor     eax, eax
0x1800052a8  jmp     loc_18000514A
0x1800052ad  mov     rax, [rcx]
0x1800052b0  mov     rax, [rax+10h]
0x1800052b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052b9  mov     [rsp+48h+arg_8], rbp
0x1800052be  jmp     loc_18000513A
0x1800052c3  mov     rax, [rcx]
0x1800052c6  mov     rax, [rax+10h]
0x1800052ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052cf  jmp     loc_180005148
```
