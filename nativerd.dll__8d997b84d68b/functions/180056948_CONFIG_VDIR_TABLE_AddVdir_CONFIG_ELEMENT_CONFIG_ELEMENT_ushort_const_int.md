# CONFIG_VDIR_TABLE::AddVdir(CONFIG_ELEMENT *,CONFIG_ELEMENT *,ushort const *,int *)

- ea: `0x180056948`
- end: `0x180056c79`
- name: `?AddVdir@CONFIG_VDIR_TABLE@@AEAAJPEAVCONFIG_ELEMENT@@0PEBGPEAH@Z`
- size: `817`
- prototype: `int(CONFIG_VDIR_TABLE *__hidden this, struct CONFIG_ELEMENT *, struct CONFIG_ELEMENT *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180056c80`

## callees

- `0x1800012c0`
- `0x180005a30`
- `0x1800079f0`
- `0x1800155a0`
- `0x18001c250`
- `0x180056290`
- `0x1800566b4`
- `0x180056948`
- `0x180056f14`
- `0x18005700c`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180056ac7`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180056ac7`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180056aa2`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180056ae4`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180056aa2`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180056ae4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056c33`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056c3e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056c33`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056c3e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056af9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056b9b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056bd6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056af9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056b9b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056bd6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800569e0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180056a0b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800569e0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180056a0b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180056a85`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180056a85`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180056a73`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180056a73`

## pseudocode

```c
__int64 __fastcall CONFIG_VDIR_TABLE::AddVdir(
        CONFIG_VDIR_TABLE *this,
        struct CONFIG_ELEMENT *a2,
        struct CONFIG_ELEMENT *a3,
        const unsigned __int16 *a4,
        int *a5)
{
  const unsigned __int16 **v9; // rax
  const unsigned __int16 **v10; // rbx
  int Directory; // edi
  const unsigned __int16 *Str; // rax
  unsigned __int16 *v13; // r14
  int v14; // eax
  unsigned __int16 *v15; // rax
  int v16; // ecx
  unsigned __int16 *v17; // rax
  int v18; // ecx
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v23[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+6Ch] [rbp-94h]
  _BYTE v26[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[56]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v28[3]; // [rsp+E0h] [rbp-20h] BYREF
  int v29; // [rsp+F8h] [rbp-8h]
  int v30; // [rsp+FCh] [rbp-4h]
  int v31; // [rsp+100h] [rbp+0h]
  char v32; // [rsp+104h] [rbp+4h] BYREF
  unsigned __int16 v33[128]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v34[264]; // [rsp+390h] [rbp+290h] BYREF

  v31 &= 0xFFFFFFF0;
  v28[0] = &v32;
  v28[1] = 0;
  v29 = -1;
  v30 = -1;
  v28[2] = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v26, v33, 0x80u);
  memset_0(v34, 0, 0x208u);
  STRU::STRU((STRU *)v27, v34, 0x104u);
  v9 = (const unsigned __int16 **)operator new(0x30u);
  v10 = v9;
  if ( v9 )
  {
    *((_DWORD *)v9 + 11) = 1;
    v9[2] = 0;
    v9[3] = 0;
    v9[4] = 0;
    *v9 = 0;
    v9[1] = 0;
    Directory = CONFIG_VDIR::Initialize((CONFIG_VDIR *)v9, a2, a3);
    if ( Directory >= 0 )
    {
      Directory = CONFIG_VDIR::GetDirectory((CONFIG_VDIR *)v10, (struct STRU *)v27);
      if ( Directory >= 0 )
      {
        STRU::Reset((STRU *)v26);
        Directory = STRU::Copy((STRU *)v26, L"/");
        if ( Directory >= 0 )
        {
          Directory = STRU::Append((STRU *)v26, v10[2], *((_DWORD *)v10 + 8));
          if ( Directory >= 0 )
          {
            if ( !*((_DWORD *)v10 + 8)
              || !*((_DWORD *)v10 + 9)
              || (Directory = STRU::Append((STRU *)v26, 0x2Fu), Directory >= 0) )
            {
              Directory = STRU::Append((STRU *)v26, v10[3], *((_DWORD *)v10 + 9));
              if ( Directory >= 0 )
              {
                Str = STRU::QueryStr((STRU *)v26);
                Directory = PATH::Parse((PATH *)v28, a4, Str);
                if ( Directory >= 0 )
                {
                  Directory = PATH::GetPathString((PATH *)v28, v29 - 1, (const unsigned __int16 **)&v21, &v20, &v22);
                  if ( Directory >= 0 )
                  {
                    v13 = v21;
                    v23[1] = v22;
                    v24 = v20;
                    v23[0] = v21;
                    v25 = 0;
                    v14 = CONFIG_HASH<CONFIG_VDIR>::Insert(
                            (CONFIG_VDIR_TABLE *)((char *)this + 120),
                            (struct CONFIG_HASH_KEY *)v23,
                            (volatile signed __int32 *)v10);
                    Directory = v14;
                    if ( v14 >= 0 )
                    {
                      if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 2) != 0 )
                      {
                        v17 = STRU::QueryStr((STRU *)v27);
                        McTemplateU0zzzzz_EtwEventWriteTransfer(
                          v18,
                          (unsigned int)NATIVERD_EVENT_VIRTUAL_DIRECTORY_MAPPING_CREATION,
                          (_DWORD)a4,
                          (unsigned int)v10[2],
                          (__int64)v10[3],
                          (__int64)v13,
                          (__int64)v17);
                      }
                      if ( a5 )
                        *a5 = a3 && !*((_DWORD *)v10 + 9);
                    }
                    else if ( v14 == -2147024713 && (Microsoft_Windows_IIS_ConfigurationEnableBits & 8) != 0 )
                    {
                      v15 = STRU::QueryStr((STRU *)v27);
                      McTemplateU0zzzzz_EtwEventWriteTransfer(
                        v16,
                        (unsigned int)NATIVERD_EVENT_VIRTUAL_DIRECTORY_IGNORED_DUE_TO_DUPLICATE_MAPPING,
                        (_DWORD)a4,
                        (unsigned int)v10[2],
                        (__int64)v10[3],
                        (__int64)v13,
                        (__int64)v15);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    CONFIG_VDIR::DereferenceConfigVDir((CONFIG_VDIR *)v10);
  }
  else
  {
    Directory = -2147024888;
  }
  STRU::~STRU((STRU *)v27);
  STRU::~STRU((STRU *)v26);
  PATH::Destroy((PATH *)v28);
  return (unsigned int)Directory;
}

```

## disassembly

```asm
0x180056948  mov     [rsp-8+arg_10], rbx
0x18005694d  push    rbp
0x18005694e  push    rsi
0x18005694f  push    rdi
0x180056950  push    r12
0x180056952  push    r13
0x180056954  push    r14
0x180056956  push    r15
0x180056958  lea     rbp, [rsp-4B0h]
0x180056960  sub     rsp, 5B0h
0x180056967  mov     rax, cs:__security_cookie
0x18005696e  xor     rax, rsp
0x180056971  mov     [rbp+4E0h+var_40], rax
0x180056978  mov     rsi, [rbp+4E0h+arg_20]
0x18005697f  lea     rax, [rbp+4E0h+var_4DC]
0x180056983  and     [rbp+4E0h+var_4E0], 0FFFFFFF0h
0x180056987  xor     r14d, r14d
0x18005698a  mov     [rbp+4E0h+var_500], rax
0x18005698e  mov     r12, r8
0x180056991  or      eax, 0FFFFFFFFh
0x180056994  mov     [rbp+4E0h+var_4F8], r14
0x180056998  mov     rdi, rdx
0x18005699b  mov     [rbp+4E0h+var_4E8], eax
0x18005699e  mov     r13, rcx
0x1800569a1  mov     [rbp+4E0h+var_4E4], eax
0x1800569a4  xor     edx, edx; Val
0x1800569a6  mov     [rbp+4E0h+var_4F0], r14
0x1800569aa  mov     r8d, 100h; Size
0x1800569b0  mov     [rsp+5E0h+var_598], r14
0x1800569b5  lea     rcx, [rbp+4E0h+var_350]; void *
0x1800569bc  mov     [rsp+5E0h+var_5A0], r14d
0x1800569c1  mov     r15, r9
0x1800569c4  mov     [rsp+5E0h+var_590], r14
0x1800569c9  call    memset_0
0x1800569ce  mov     r8d, 80h
0x1800569d4  lea     rdx, [rbp+4E0h+var_350]
0x1800569db  lea     rcx, [rsp+5E0h+var_570]
0x1800569e0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800569e6  xor     edx, edx; Val
0x1800569e8  lea     rcx, [rbp+4E0h+var_250]; void *
0x1800569ef  mov     r8d, 208h; Size
0x1800569f5  call    memset_0
0x1800569fa  mov     r8d, 104h
0x180056a00  lea     rdx, [rbp+4E0h+var_250]
0x180056a07  lea     rcx, [rbp+4E0h+var_538]
0x180056a0b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180056a11  lea     ecx, [r14+30h]; Size
0x180056a15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180056a1a  mov     rbx, rax
0x180056a1d  test    rax, rax
0x180056a20  jz      loc_180056C2A
0x180056a26  mov     r8, r12; struct CONFIG_ELEMENT *
0x180056a29  mov     dword ptr [rax+2Ch], 1
0x180056a30  mov     rdx, rdi; struct CONFIG_ELEMENT *
0x180056a33  mov     [rax+10h], r14
0x180056a37  mov     rcx, rax; this
0x180056a3a  mov     [rax+18h], r14
0x180056a3e  mov     [rax+20h], r14
0x180056a42  mov     [rax], r14
0x180056a45  mov     [rax+8], r14
0x180056a49  call    ?Initialize@CONFIG_VDIR@@QEAAJPEAVCONFIG_ELEMENT@@0@Z; CONFIG_VDIR::Initialize(CONFIG_ELEMENT *,CONFIG_ELEMENT *)
0x180056a4e  mov     edi, eax
0x180056a50  test    eax, eax
0x180056a52  js      loc_180056C20
0x180056a58  lea     rdx, [rbp+4E0h+var_538]; struct STRU *
0x180056a5c  mov     rcx, rbx; this
0x180056a5f  call    ?GetDirectory@CONFIG_VDIR@@QEAAJPEAVSTRU@@@Z; CONFIG_VDIR::GetDirectory(STRU *)
0x180056a64  mov     edi, eax
0x180056a66  test    eax, eax
0x180056a68  js      loc_180056C20
0x180056a6e  lea     rcx, [rsp+5E0h+var_570]
0x180056a73  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180056a79  lea     rdx, asc_18005F044; "/"
0x180056a80  lea     rcx, [rsp+5E0h+var_570]
0x180056a85  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180056a8b  mov     edi, eax
0x180056a8d  test    eax, eax
0x180056a8f  js      loc_180056C20
0x180056a95  mov     r8d, [rbx+20h]
0x180056a99  lea     rcx, [rsp+5E0h+var_570]
0x180056a9e  mov     rdx, [rbx+10h]
0x180056aa2  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180056aa8  mov     edi, eax
0x180056aaa  test    eax, eax
0x180056aac  js      loc_180056C20
0x180056ab2  cmp     [rbx+20h], r14d
0x180056ab6  jz      short loc_180056AD7
0x180056ab8  cmp     [rbx+24h], r14d
0x180056abc  jz      short loc_180056AD7
0x180056abe  lea     edx, [r14+2Fh]
0x180056ac2  lea     rcx, [rsp+5E0h+var_570]
0x180056ac7  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180056acd  mov     edi, eax
0x180056acf  test    eax, eax
0x180056ad1  js      loc_180056C20
0x180056ad7  mov     r8d, [rbx+24h]
0x180056adb  lea     rcx, [rsp+5E0h+var_570]
0x180056ae0  mov     rdx, [rbx+18h]
0x180056ae4  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180056aea  mov     edi, eax
0x180056aec  test    eax, eax
0x180056aee  js      loc_180056C20
0x180056af4  lea     rcx, [rsp+5E0h+var_570]
0x180056af9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180056aff  mov     rdx, r15; unsigned __int16 *
0x180056b02  lea     rcx, [rbp+4E0h+var_500]; this
0x180056b06  mov     r8, rax; unsigned __int16 *
0x180056b09  call    ?Parse@PATH@@QEAAJPEBG0@Z; PATH::Parse(ushort const *,ushort const *)
0x180056b0e  mov     edi, eax
0x180056b10  test    eax, eax
0x180056b12  js      loc_180056C20
0x180056b18  mov     edx, [rbp+4E0h+var_4E8]
0x180056b1b  lea     rax, [rsp+5E0h+var_590]
0x180056b20  dec     edx; unsigned int
0x180056b22  mov     [rsp+5E0h+var_5C0], rax; unsigned __int64 *
0x180056b27  lea     r9, [rsp+5E0h+var_5A0]; unsigned int *
0x180056b2c  lea     r8, [rsp+5E0h+var_598]; unsigned __int16 **
0x180056b31  lea     rcx, [rbp+4E0h+var_500]; this
0x180056b35  call    ?GetPathString@PATH@@QEAAJKPEAPEBGPEAKPEA_K@Z; PATH::GetPathString(ulong,ushort const * *,ulong *,unsigned __int64 *)
0x180056b3a  mov     edi, eax
0x180056b3c  test    eax, eax
0x180056b3e  js      loc_180056C20
0x180056b44  mov     rax, [rsp+5E0h+var_590]
0x180056b49  lea     rcx, [r13+78h]; this
0x180056b4d  mov     r14, [rsp+5E0h+var_598]
0x180056b52  lea     rdx, [rsp+5E0h+var_588]; struct CONFIG_HASH_KEY *
0x180056b57  mov     [rsp+5E0h+var_580], rax
0x180056b5c  mov     r8, rbx; void *
0x180056b5f  mov     eax, [rsp+5E0h+var_5A0]
0x180056b63  mov     [rsp+5E0h+var_578], eax
0x180056b67  mov     [rsp+5E0h+var_588], r14
0x180056b6c  mov     [rsp+5E0h+var_574], 0
0x180056b74  call    ?Insert@?$CONFIG_HASH@VCONFIG_VDIR@@@@QEAAJPEAVCONFIG_HASH_KEY@@PEAVCONFIG_VDIR@@H@Z; CONFIG_HASH<CONFIG_VDIR>::Insert(CONFIG_HASH_KEY *,CONFIG_VDIR *,int)
0x180056b79  mov     edi, eax
0x180056b7b  test    eax, eax
0x180056b7d  jns     short loc_180056BC9
0x180056b7f  cmp     eax, 800700B7h
0x180056b84  jnz     loc_180056C20
0x180056b8a  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 8
0x180056b91  jz      loc_180056C20
0x180056b97  lea     rcx, [rbp+4E0h+var_538]
0x180056b9b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180056ba1  mov     r9, [rbx+10h]
0x180056ba5  lea     rdx, NATIVERD_EVENT_VIRTUAL_DIRECTORY_IGNORED_DUE_TO_DUPLICATE_MAPPING
0x180056bac  mov     [rsp+5E0h+var_5B0], rax
0x180056bb1  mov     r8, r15
0x180056bb4  mov     rax, [rbx+18h]
0x180056bb8  mov     [rsp+5E0h+var_5B8], r14
0x180056bbd  mov     [rsp+5E0h+var_5C0], rax
0x180056bc2  call    McTemplateU0zzzzz_EtwEventWriteTransfer
0x180056bc7  jmp     short loc_180056C20
0x180056bc9  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 2
0x180056bd0  jz      short loc_180056C02
0x180056bd2  lea     rcx, [rbp+4E0h+var_538]
0x180056bd6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180056bdc  mov     r9, [rbx+10h]
0x180056be0  lea     rdx, NATIVERD_EVENT_VIRTUAL_DIRECTORY_MAPPING_CREATION
0x180056be7  mov     [rsp+5E0h+var_5B0], rax
0x180056bec  mov     r8, r15
0x180056bef  mov     rax, [rbx+18h]
0x180056bf3  mov     [rsp+5E0h+var_5B8], r14
0x180056bf8  mov     [rsp+5E0h+var_5C0], rax
0x180056bfd  call    McTemplateU0zzzzz_EtwEventWriteTransfer
0x180056c02  test    rsi, rsi
0x180056c05  jz      short loc_180056C20
0x180056c07  test    r12, r12
0x180056c0a  jz      short loc_180056C1A
0x180056c0c  cmp     dword ptr [rbx+24h], 0
0x180056c10  jnz     short loc_180056C1A
0x180056c12  mov     dword ptr [rsi], 1
0x180056c18  jmp     short loc_180056C20
0x180056c1a  mov     dword ptr [rsi], 0
0x180056c20  mov     rcx, rbx; this
0x180056c23  call    ?DereferenceConfigVDir@CONFIG_VDIR@@QEAAXXZ; CONFIG_VDIR::DereferenceConfigVDir(void)
0x180056c28  jmp     short loc_180056C2F
0x180056c2a  mov     edi, 80070008h
0x180056c2f  lea     rcx, [rbp+4E0h+var_538]
0x180056c33  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180056c39  lea     rcx, [rsp+5E0h+var_570]
0x180056c3e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180056c44  lea     rcx, [rbp+4E0h+var_500]; this
0x180056c48  call    ?Destroy@PATH@@QEAAXXZ; PATH::Destroy(void)
0x180056c4d  mov     eax, edi
0x180056c4f  mov     rcx, [rbp+4E0h+var_40]
0x180056c56  xor     rcx, rsp; StackCookie
0x180056c59  call    __security_check_cookie
0x180056c5e  mov     rbx, [rsp+5E0h+arg_10]
0x180056c66  add     rsp, 5B0h
0x180056c6d  pop     r15
0x180056c6f  pop     r14
0x180056c71  pop     r13
0x180056c73  pop     r12
0x180056c75  pop     rdi
0x180056c76  pop     rsi
0x180056c77  pop     rbp
0x180056c78  retn
```
