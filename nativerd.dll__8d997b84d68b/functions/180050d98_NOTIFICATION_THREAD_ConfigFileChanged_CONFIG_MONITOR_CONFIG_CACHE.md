# NOTIFICATION_THREAD::ConfigFileChanged(CONFIG_MONITOR *,CONFIG_CACHE *)

- ea: `0x180050d98`
- end: `0x180050f63`
- name: `?ConfigFileChanged@NOTIFICATION_THREAD@@CAHPEAUCONFIG_MONITOR@@PEAVCONFIG_CACHE@@@Z`
- size: `459`
- prototype: `static int(struct CONFIG_MONITOR *, struct CONFIG_CACHE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180051510`

## callees

- `0x1800012c0`
- `0x180003480`
- `0x180017850`
- `0x18004e9fc`
- `0x18004f07c`
- `0x180050d98`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180050eb3`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180050eb3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180050f29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180050f29`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180050edd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180050edd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180050e20`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180050e20`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180050e76`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180050e76`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180050ec8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180050ec8`

## pseudocode

```c
__int64 __fastcall NOTIFICATION_THREAD::ConfigFileChanged(const unsigned __int16 **a1, struct CONFIG_CACHE *a2)
{
  unsigned int v4; // r14d
  int ConfigFile; // ebx
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rax
  unsigned __int16 *v8; // rbx
  const unsigned __int16 *Str; // rax
  int FileChanged; // eax
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  CONFIG_FILE *v13; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[64]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[3]; // [rsp+90h] [rbp-70h] BYREF
  int v16; // [rsp+A8h] [rbp-58h]
  int v17; // [rsp+ACh] [rbp-54h]
  int v18; // [rsp+B0h] [rbp-50h]
  char v19; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned __int16 v20[264]; // [rsp+240h] [rbp+140h] BYREF

  v18 &= 0xFFFFFFF0;
  v15[0] = &v19;
  v12 = 0;
  v16 = -1;
  v17 = -1;
  v13 = 0;
  v15[1] = 0;
  v15[2] = 0;
  v4 = 0;
  memset_0(v20, 0, 0x208u);
  STRU::STRU((STRU *)v14, v20, 0x104u);
  if ( (int)PATH::Parse((PATH *)v15, *a1) < 0 )
    goto LABEL_13;
  ConfigFile = CONFIG_CACHE::GetConfigFile(a2, (struct PATH *)v15, 0x10u, &v13, 0, 0, 0, 0);
  if ( ConfigFile >= 0 )
  {
    ConfigFile = STRU::Copy((STRU *)v14, a1[1]);
    if ( ConfigFile >= 0 )
    {
      v6 = a1[1];
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      if ( v6[(unsigned int)(v7 - 1)] == 92 || (ConfigFile = STRU::Append((STRU *)v14, L"\\", 1u), ConfigFile >= 0) )
      {
        ConfigFile = STRU::Append((STRU *)v14, a1[2]);
        if ( ConfigFile >= 0 )
        {
          v8 = (unsigned __int16 *)a1[4];
          Str = STRU::QueryStr((STRU *)v14);
          FileChanged = CONFIG_CACHE::GetFileChanged((CONFIG_CACHE *)&v12, v13, *a1, Str, v8, &v12);
          v4 = v12;
          ConfigFile = FileChanged;
        }
      }
    }
  }
  if ( v13 )
    CONFIG_FILE::DereferenceConfigFile(v13);
  if ( ConfigFile < 0 )
LABEL_13:
    v4 = 1;
  STRU::~STRU((STRU *)v14);
  PATH::Destroy((PATH *)v15);
  return v4;
}

```

## disassembly

```asm
0x180050d98  mov     [rsp-8+arg_10], rbx
0x180050d9d  mov     [rsp-8+arg_18], rdi
0x180050da2  push    rbp
0x180050da3  push    r14
0x180050da5  push    r15
0x180050da7  lea     rbp, [rsp-360h]
0x180050daf  sub     rsp, 460h
0x180050db6  mov     rax, cs:__security_cookie
0x180050dbd  xor     rax, rsp
0x180050dc0  mov     [rbp+370h+var_20], rax
0x180050dc7  and     [rbp+370h+var_3C0], 0FFFFFFF0h
0x180050dcb  lea     rax, [rbp+370h+var_3BC]
0x180050dcf  xor     r15d, r15d
0x180050dd2  mov     [rbp+370h+var_3E0], rax
0x180050dd6  or      eax, 0FFFFFFFFh
0x180050dd9  mov     [rsp+470h+var_430], r15d
0x180050dde  mov     rbx, rdx
0x180050de1  mov     [rbp+370h+var_3C8], eax
0x180050de4  mov     rdi, rcx
0x180050de7  mov     [rbp+370h+var_3C4], eax
0x180050dea  xor     edx, edx; Val
0x180050dec  mov     [rsp+470h+var_428], r15
0x180050df1  mov     r8d, 208h; Size
0x180050df7  mov     [rbp+370h+var_3D8], r15
0x180050dfb  lea     rcx, [rbp+370h+var_230]; void *
0x180050e02  mov     [rbp+370h+var_3D0], r15
0x180050e06  mov     r14d, r15d
0x180050e09  call    memset_0
0x180050e0e  mov     r8d, 104h
0x180050e14  lea     rdx, [rbp+370h+var_230]
0x180050e1b  lea     rcx, [rsp+470h+var_420]
0x180050e20  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180050e26  mov     rdx, [rdi]; unsigned __int16 *
0x180050e29  lea     rcx, [rbp+370h+var_3E0]; this
0x180050e2d  call    ?Parse@PATH@@QEAAJPEBG@Z; PATH::Parse(ushort const *)
0x180050e32  test    eax, eax
0x180050e34  js      loc_180050F1E
0x180050e3a  mov     [rsp+470h+var_438], r15; struct PARSE_ERROR_INFO *
0x180050e3f  lea     r9, [rsp+470h+var_428]; struct CONFIG_FILE **
0x180050e44  mov     [rsp+470h+var_440], r15; unsigned int *
0x180050e49  lea     r8d, [r15+10h]; unsigned int
0x180050e4d  mov     [rsp+470h+var_448], r15; void **
0x180050e52  lea     rdx, [rbp+370h+var_3E0]; struct PATH *
0x180050e56  mov     rcx, rbx; this
0x180050e59  mov     [rsp+470h+var_450], r15; struct STRU *
0x180050e5e  call    ?GetConfigFile@CONFIG_CACHE@@QEAAJPEAVPATH@@KPEAPEAVCONFIG_FILE@@PEAVSTRU@@PEAPEAXPEAKPEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::GetConfigFile(PATH *,ulong,CONFIG_FILE * *,STRU *,void * *,ulong *,PARSE_ERROR_INFO *)
0x180050e63  mov     ebx, eax
0x180050e65  test    eax, eax
0x180050e67  js      loc_180050F09
0x180050e6d  mov     rdx, [rdi+8]
0x180050e71  lea     rcx, [rsp+470h+var_420]
0x180050e76  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180050e7c  mov     ebx, eax
0x180050e7e  test    eax, eax
0x180050e80  js      loc_180050F09
0x180050e86  mov     rdx, [rdi+8]
0x180050e8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180050e8e  inc     rax
0x180050e91  cmp     [rdx+rax*2], r15w
0x180050e96  jnz     short loc_180050E8E
0x180050e98  dec     eax
0x180050e9a  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x180050e9f  jz      short loc_180050EBF
0x180050ea1  mov     r8d, 1
0x180050ea7  lea     rdx, asc_18005F940; "\\"
0x180050eae  lea     rcx, [rsp+470h+var_420]
0x180050eb3  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180050eb9  mov     ebx, eax
0x180050ebb  test    eax, eax
0x180050ebd  js      short loc_180050F09
0x180050ebf  mov     rdx, [rdi+10h]
0x180050ec3  lea     rcx, [rsp+470h+var_420]
0x180050ec8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180050ece  mov     ebx, eax
0x180050ed0  test    eax, eax
0x180050ed2  js      short loc_180050F09
0x180050ed4  mov     rbx, [rdi+20h]
0x180050ed8  lea     rcx, [rsp+470h+var_420]
0x180050edd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180050ee3  mov     r8, [rdi]; unsigned __int16 *
0x180050ee6  lea     rcx, [rsp+470h+var_430]; this
0x180050eeb  mov     rdx, [rsp+470h+var_428]; struct CONFIG_FILE *
0x180050ef0  mov     r9, rax; unsigned __int16 *
0x180050ef3  mov     [rsp+470h+var_448], rcx; int *
0x180050ef8  mov     [rsp+470h+var_450], rbx; void *
0x180050efd  call    ?GetFileChanged@CONFIG_CACHE@@QEAAJPEAVCONFIG_FILE@@PEBG1PEAXPEAH@Z; CONFIG_CACHE::GetFileChanged(CONFIG_FILE *,ushort const *,ushort const *,void *,int *)
0x180050f02  mov     r14d, [rsp+470h+var_430]
0x180050f07  mov     ebx, eax
0x180050f09  cmp     [rsp+470h+var_428], r15
0x180050f0e  jz      short loc_180050F1A
0x180050f10  mov     rcx, [rsp+470h+var_428]; this
0x180050f15  call    ?DereferenceConfigFile@CONFIG_FILE@@QEAAXXZ; CONFIG_FILE::DereferenceConfigFile(void)
0x180050f1a  test    ebx, ebx
0x180050f1c  jns     short loc_180050F24
0x180050f1e  mov     r14d, 1
0x180050f24  lea     rcx, [rsp+470h+var_420]
0x180050f29  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180050f2f  lea     rcx, [rbp+370h+var_3E0]; this
0x180050f33  call    ?Destroy@PATH@@QEAAXXZ; PATH::Destroy(void)
0x180050f38  mov     eax, r14d
0x180050f3b  mov     rcx, [rbp+370h+var_20]
0x180050f42  xor     rcx, rsp; StackCookie
0x180050f45  call    __security_check_cookie
0x180050f4a  lea     r11, [rsp+470h+var_10]
0x180050f52  mov     rbx, [r11+30h]
0x180050f56  mov     rdi, [r11+38h]
0x180050f5a  mov     rsp, r11
0x180050f5d  pop     r15
0x180050f5f  pop     r14
0x180050f61  pop     rbp
0x180050f62  retn
```
