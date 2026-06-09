# GetMultiSzRegistryValueToWrite(IIS_SETUP_REGISTRY_ENTRY *,BUFFER *,ulong *)

- ea: `0x180001d7c`
- end: `0x180002005`
- name: `?GetMultiSzRegistryValueToWrite@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVBUFFER@@PEAK@Z`
- size: `649`
- prototype: `__int64 __fastcall(struct IIS_SETUP_REGISTRY_ENTRY *, struct BUFFER *this, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18000224c`

## callees

- `0x180001ab0`
- `0x180001d7c`
- `0x18000260c`
- `0x18000283c`
- `0x180002ff8`
- `0x180003024`
- `0x1800033ac`
- `0x1800034b8`
- `0x180003605`
- `0x180003650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001fab`
- `KERNEL32!GetLastError` at `0x180001fab`

## pseudocode

```c
__int64 __fastcall GetMultiSzRegistryValueToWrite(struct IIS_SETUP_REGISTRY_ENTRY *a1, void **this, unsigned int *a3)
{
  _QWORD *v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rdx
  __int64 v9; // rcx
  signed int SetupRegistryEntryAsMultiSz; // ebx
  HKEY v11; // rax
  MULTISZ *v12; // rsi
  _QWORD *v13; // rcx
  const unsigned __int16 *v14; // rdi
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 i; // rdx
  const unsigned __int16 *v18; // rdx
  size_t v19; // r8
  __int64 j; // r9
  void *v21; // rdx
  unsigned int v22; // eax
  signed int LastError; // eax
  _QWORD v25[4]; // [rsp+20h] [rbp-59h] BYREF
  void *Src; // [rsp+40h] [rbp-39h]
  int v27; // [rsp+48h] [rbp-31h]
  __int16 v28; // [rsp+4Ch] [rbp-2Dh]
  __int64 v29; // [rsp+50h] [rbp-29h]
  _QWORD v30[4]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD *v31; // [rsp+78h] [rbp-1h]
  int v32; // [rsp+80h] [rbp+7h]
  __int16 v33; // [rsp+84h] [rbp+Bh]
  __int64 v34; // [rsp+88h] [rbp+Fh]

  v28 = 256;
  v25[0] = 0;
  v6 = v25;
  v7 = 0;
  Src = v25;
  v27 = 32;
  while ( 1 )
  {
    *((_WORD *)v6 + v7++) = 0;
    if ( v7 == 2 )
      break;
    v6 = Src;
  }
  v8 = v30;
  v29 = 2;
  v31 = v30;
  v9 = 0;
  v30[0] = 0;
  v32 = 32;
  v33 = 256;
  while ( 1 )
  {
    *((_WORD *)v8 + v9++) = 0;
    if ( v9 == 2 )
      break;
    v8 = v31;
  }
  v34 = 2;
  if ( !a1 || !this || !a3 )
  {
    SetupRegistryEntryAsMultiSz = -2147024809;
    goto LABEL_43;
  }
  SetupRegistryEntryAsMultiSz = ReadSetupRegistryEntryAsMultiSz(a1, (struct MULTISZ *)v25);
  if ( SetupRegistryEntryAsMultiSz < 0 )
    goto LABEL_43;
  if ( (unsigned int)(*((_DWORD *)a1 + 13) - 1) > 1 )
    goto LABEL_37;
  v11 = ConvertStringToHKey(*((wchar_t **)a1 + 1));
  SetupRegistryEntryAsMultiSz = ReadMultiSzRegistryValue(
                                  v11,
                                  *((LPCWSTR *)a1 + 2),
                                  *((LPCWSTR *)a1 + 3),
                                  (struct MULTISZ *)v30);
  if ( SetupRegistryEntryAsMultiSz < 0 )
  {
    SetupRegistryEntryAsMultiSz = 0;
    goto LABEL_37;
  }
  if ( *((_DWORD *)a1 + 13) == 1 )
  {
    v12 = (MULTISZ *)v30;
    v13 = v25;
  }
  else if ( *((_DWORD *)a1 + 13) == 2 )
  {
    v12 = (MULTISZ *)v25;
    v13 = v30;
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  v14 = (const unsigned __int16 *)(v13[4] & -(__int64)(*(_WORD *)v13[4] != 0));
  if ( v14 )
  {
    while ( 1 )
    {
      if ( !MULTISZ::FindStringNoCase(v12, v14) )
      {
        if ( v14 )
        {
          v15 = -1;
          do
            ++v15;
          while ( v14[v15] );
          if ( !(unsigned int)MULTISZ::AuxAppend(v12, v14, (unsigned int)(2 * v15), 1) )
            break;
        }
      }
      v16 = -1;
      do
        ++v16;
      while ( v14[v16] );
      v14 += v16 + 1;
      if ( !*v14 )
        goto LABEL_28;
    }
  }
  else
  {
LABEL_28:
    if ( v12 == (MULTISZ *)v25 )
      goto LABEL_37;
    for ( i = 0; i != 2; ++i )
      *((_WORD *)Src + i) = 0;
    v29 = 2;
    v18 = (const unsigned __int16 *)*((_QWORD *)v12 + 4);
    v19 = (unsigned int)(2 * *((_DWORD *)v12 + 12));
    if ( Src )
    {
      for ( j = 0; j != 2; ++j )
        *((_WORD *)Src + j) = 0;
      v29 = 2;
    }
    if ( !v18 || (unsigned int)MULTISZ::AuxAppend((MULTISZ *)v25, v18, v19, 0) )
    {
LABEL_37:
      if ( (unsigned int)(2 * v29) <= *((_DWORD *)this + 10) || BUFFER::ReallocStorage((BUFFER *)this, 2 * v29) )
      {
        v21 = Src;
        v22 = 2 * v29;
        *a3 = 2 * v29;
        memcpy_0(this[4], v21, v22);
        goto LABEL_43;
      }
    }
  }
  LastError = GetLastError();
  SetupRegistryEntryAsMultiSz = LastError;
  if ( LastError > 0 )
    SetupRegistryEntryAsMultiSz = (unsigned __int16)LastError | 0x80070000;
LABEL_43:
  if ( (_BYTE)v33 )
    BUFFER::FreeMemoryInternal((BUFFER *)v30);
  if ( (_BYTE)v28 )
    BUFFER::FreeMemoryInternal((BUFFER *)v25);
  return (unsigned int)SetupRegistryEntryAsMultiSz;
}

```

## disassembly

```asm
0x180001d7c  push    rbp
0x180001d7e  push    rbx
0x180001d7f  push    rsi
0x180001d80  push    rdi
0x180001d81  push    r12
0x180001d83  push    r14
0x180001d85  push    r15
0x180001d87  lea     rbp, [rsp-27h]
0x180001d8c  sub     rsp, 0A0h
0x180001d93  mov     rax, cs:__security_cookie
0x180001d9a  xor     rax, rsp
0x180001d9d  mov     [rbp+57h+var_40], rax
0x180001da1  xor     r12d, r12d
0x180001da4  mov     [rbp+57h+var_84], 100h
0x180001daa  mov     r15, r8
0x180001dad  mov     [rbp+57h+var_B0], r12
0x180001db1  mov     r14, rdx
0x180001db4  mov     rdi, rcx
0x180001db7  lea     rdx, [rbp+57h+var_B0]
0x180001dbb  mov     ecx, r12d
0x180001dbe  lea     r8d, [r12+20h]
0x180001dc3  mov     [rbp+57h+Src], rdx
0x180001dc7  mov     [rbp+57h+var_88], r8d
0x180001dcb  mov     [rdx+rcx*2], r12w
0x180001dd0  inc     rcx
0x180001dd3  cmp     rcx, 2
0x180001dd7  jz      short loc_180001DDF
0x180001dd9  mov     rdx, [rbp+57h+Src]
0x180001ddd  jmp     short loc_180001DCB
0x180001ddf  lea     rdx, [rbp+57h+var_78]
0x180001de3  mov     [rbp+57h+var_80], 2
0x180001deb  mov     [rbp+57h+var_58], rdx
0x180001def  mov     rcx, r12
0x180001df2  mov     [rbp+57h+var_78], r12
0x180001df6  mov     [rbp+57h+var_50], r8d
0x180001dfa  mov     [rbp+57h+var_4C], 100h
0x180001e00  mov     [rdx+rcx*2], r12w
0x180001e05  inc     rcx
0x180001e08  cmp     rcx, 2
0x180001e0c  jz      short loc_180001E14
0x180001e0e  mov     rdx, [rbp+57h+var_58]
0x180001e12  jmp     short loc_180001E00
0x180001e14  mov     [rbp+57h+var_48], 2
0x180001e1c  test    rdi, rdi
0x180001e1f  jz      loc_180001FC2
0x180001e25  test    r14, r14
0x180001e28  jz      loc_180001FC2
0x180001e2e  test    r15, r15
0x180001e31  jz      loc_180001FC2
0x180001e37  lea     rdx, [rbp+57h+var_B0]; struct MULTISZ *
0x180001e3b  mov     rcx, rdi; struct IIS_SETUP_REGISTRY_ENTRY *
0x180001e3e  call    ?ReadSetupRegistryEntryAsMultiSz@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVMULTISZ@@@Z; ReadSetupRegistryEntryAsMultiSz(IIS_SETUP_REGISTRY_ENTRY *,MULTISZ *)
0x180001e43  mov     ebx, eax
0x180001e45  test    eax, eax
0x180001e47  js      loc_180001FC7
0x180001e4d  mov     ecx, [rdi+34h]
0x180001e50  dec     ecx
0x180001e52  cmp     ecx, 1
0x180001e55  ja      loc_180001F79
0x180001e5b  mov     rcx, [rdi+8]; String1
0x180001e5f  call    ?ConvertStringToHKey@@YAPEAUHKEY__@@PEAG@Z; ConvertStringToHKey(ushort *)
0x180001e64  mov     r8, [rdi+18h]; lpValueName
0x180001e68  lea     r9, [rbp+57h+var_78]; this
0x180001e6c  mov     rdx, [rdi+10h]; lpSubKey
0x180001e70  mov     rcx, rax; hKey
0x180001e73  call    ?ReadMultiSzRegistryValue@@YAJPEAUHKEY__@@PEAG1PEAVMULTISZ@@@Z; ReadMultiSzRegistryValue(HKEY__ *,ushort *,ushort *,MULTISZ *)
0x180001e78  mov     ebx, eax
0x180001e7a  test    eax, eax
0x180001e7c  jns     short loc_180001E86
0x180001e7e  mov     ebx, r12d
0x180001e81  jmp     loc_180001F79
0x180001e86  cmp     dword ptr [rdi+34h], 1
0x180001e8a  jnz     short loc_180001E96
0x180001e8c  lea     rsi, [rbp+57h+var_78]
0x180001e90  lea     rcx, [rbp+57h+var_B0]
0x180001e94  jmp     short loc_180001EAC
0x180001e96  cmp     dword ptr [rdi+34h], 2
0x180001e9a  jnz     short loc_180001EA6
0x180001e9c  lea     rsi, [rbp+57h+var_B0]
0x180001ea0  lea     rcx, [rbp+57h+var_78]
0x180001ea4  jmp     short loc_180001EAC
0x180001ea6  mov     rsi, r12
0x180001ea9  mov     rcx, r12
0x180001eac  mov     rcx, [rcx+20h]
0x180001eb0  movzx   eax, word ptr [rcx]
0x180001eb3  neg     ax
0x180001eb6  sbb     rdi, rdi
0x180001eb9  and     rdi, rcx
0x180001ebc  jz      short loc_180001F18
0x180001ebe  mov     rdx, rdi; unsigned __int16 *
0x180001ec1  mov     rcx, rsi; this
0x180001ec4  call    ?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindStringNoCase(ushort const *)
0x180001ec9  test    eax, eax
0x180001ecb  jnz     short loc_180001EFC
0x180001ecd  test    rdi, rdi
0x180001ed0  jz      short loc_180001EFC
0x180001ed2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180001ed6  inc     r8
0x180001ed9  cmp     [rdi+r8*2], r12w
0x180001ede  jnz     short loc_180001ED6
0x180001ee0  add     r8d, r8d; Size
0x180001ee3  mov     r9d, 1; int
0x180001ee9  mov     rdx, rdi; Src
0x180001eec  mov     rcx, rsi; this
0x180001eef  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x180001ef4  test    eax, eax
0x180001ef6  jz      loc_180001FAB
0x180001efc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001f00  inc     rax
0x180001f03  cmp     [rdi+rax*2], r12w
0x180001f08  jnz     short loc_180001F00
0x180001f0a  lea     rdi, [rdi+rax*2]
0x180001f0e  add     rdi, 2
0x180001f12  cmp     [rdi], r12w
0x180001f16  jnz     short loc_180001EBE
0x180001f18  lea     rax, [rbp+57h+var_B0]
0x180001f1c  cmp     rsi, rax
0x180001f1f  jz      short loc_180001F79
0x180001f21  mov     rdx, r12
0x180001f24  mov     rax, [rbp+57h+Src]
0x180001f28  mov     [rax+rdx*2], r12w
0x180001f2d  inc     rdx
0x180001f30  cmp     rdx, 2
0x180001f34  jnz     short loc_180001F24
0x180001f36  mov     [rbp+57h+var_80], rdx
0x180001f3a  mov     eax, [rsi+30h]
0x180001f3d  mov     rdx, [rsi+20h]; Src
0x180001f41  lea     r8d, [rax+rax]; Size
0x180001f45  cmp     [rbp+57h+Src], r12
0x180001f49  jz      short loc_180001F64
0x180001f4b  mov     r9, r12
0x180001f4e  mov     rax, [rbp+57h+Src]
0x180001f52  mov     [rax+r9*2], r12w
0x180001f57  inc     r9
0x180001f5a  cmp     r9, 2
0x180001f5e  jnz     short loc_180001F4E
0x180001f60  mov     [rbp+57h+var_80], r9
0x180001f64  test    rdx, rdx
0x180001f67  jz      short loc_180001F79
0x180001f69  xor     r9d, r9d; int
0x180001f6c  lea     rcx, [rbp+57h+var_B0]; this
0x180001f70  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x180001f75  test    eax, eax
0x180001f77  jz      short loc_180001FAB
0x180001f79  mov     eax, dword ptr [rbp+57h+var_80]
0x180001f7c  lea     edx, [rax+rax]; unsigned int
0x180001f7f  cmp     edx, [r14+28h]
0x180001f83  jbe     short loc_180001F91
0x180001f85  mov     rcx, r14; this
0x180001f88  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180001f8d  test    al, al
0x180001f8f  jz      short loc_180001FAB
0x180001f91  mov     eax, dword ptr [rbp+57h+var_80]
0x180001f94  mov     rdx, [rbp+57h+Src]; Src
0x180001f98  add     eax, eax
0x180001f9a  mov     [r15], eax
0x180001f9d  mov     rcx, [r14+20h]; void *
0x180001fa1  mov     r8d, eax; Size
0x180001fa4  call    memcpy_0
0x180001fa9  jmp     short loc_180001FC7
0x180001fab  call    cs:__imp_GetLastError
0x180001fb1  mov     ebx, eax
0x180001fb3  test    eax, eax
0x180001fb5  jle     short loc_180001FC7
0x180001fb7  movzx   ebx, ax
0x180001fba  or      ebx, 80070000h
0x180001fc0  jmp     short loc_180001FC7
0x180001fc2  mov     ebx, 80070057h
0x180001fc7  cmp     byte ptr [rbp+57h+var_4C], r12b
0x180001fcb  jz      short loc_180001FD6
0x180001fcd  lea     rcx, [rbp+57h+var_78]; this
0x180001fd1  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180001fd6  cmp     byte ptr [rbp+57h+var_84], r12b
0x180001fda  jz      short loc_180001FE5
0x180001fdc  lea     rcx, [rbp+57h+var_B0]; this
0x180001fe0  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180001fe5  mov     eax, ebx
0x180001fe7  mov     rcx, [rbp+57h+var_40]
0x180001feb  xor     rcx, rsp; StackCookie
0x180001fee  call    __security_check_cookie
0x180001ff3  add     rsp, 0A0h
0x180001ffa  pop     r15
0x180001ffc  pop     r14
0x180001ffe  pop     r12
0x180002000  pop     rdi
0x180002001  pop     rsi
0x180002002  pop     rbx
0x180002003  pop     rbp
0x180002004  retn
```
