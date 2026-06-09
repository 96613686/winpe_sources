# CSources::_Init(void)

- ea: `0x180004b7c`
- end: `0x180004f2c`
- name: `?_Init@CSources@@AEAAJXZ`
- size: `944`
- prototype: `__int64 __fastcall(CSources *__hidden this)`
- caller_count: `7`
- callee_count: `16`
- tags: `file_ops, service_task`

## callers

- `0x180004710`
- `0x1800047bc`
- `0x18000d814`
- `0x18000f09c`
- `0x1800150a0`
- `0x180020160`
- `0x180020ce4`

## callees

- `0x180002928`
- `0x180002bb8`
- `0x1800046a8`
- `0x180004a24`
- `0x180004b7c`
- `0x180004f34`
- `0x18001abd8`
- `0x18001ac04`
- `0x18001ae60`
- `0x18001aebc`
- `0x18001b050`
- `0x18001dfcc`
- `0x18001fcf0`
- `0x180022292`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180004ec0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004ec0`
- `KERNEL32!lstrcmpiW` at `0x180004e7f`
- `KERNEL32!lstrcmpiW` at `0x180004e7f`

## string_xrefs

- `0x180004c21`: `SYSTEM\CurrentControlSet\Services\EventLog`
- `0x180004c88`: `SYSTEM\CurrentControlSet\Services\EventLog`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSources::_Init(CSources *this)
{
  __int64 result; // rax
  int RemoteSystemRoot; // ebx
  HCURSOR v4; // r8
  unsigned __int16 *v5; // r12
  const WCHAR *v6; // rdx
  char v7; // r15
  int Str; // ebx
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rax
  int v11; // eax
  const unsigned __int16 *v12; // r14
  unsigned int v13; // ebx
  HKEY v14; // rsi
  const WCHAR *v15; // rax
  __int64 v16; // rdx
  const unsigned __int16 *v17; // r8
  struct CDLink *v18; // rdx
  __int64 v19; // rax
  HKEY v20; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v21; // [rsp+28h] [rbp-D8h] BYREF
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v23; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String2; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[526]; // [rsp+52h] [rbp-AEh] BYREF
  unsigned __int16 v27; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v28[526]; // [rsp+262h] [rbp+162h] BYREF

  result = *((unsigned int *)this + 1);
  if ( !(_DWORD)result )
  {
    RemoteSystemRoot = 0;
    v23 = 0;
    v20 = 0;
    phkResult = 0;
    String2 = 0;
    memset_0(v26, 0, 0x208u);
    v27 = 0;
    memset_0(v28, 0, 0x206u);
    v5 = 0;
    v6 = (const WCHAR *)*((_QWORD *)this + 1);
    if ( *v6 )
    {
      RemoteSystemRoot = CSafeReg::Connect(&phkResult, v6, v4);
      if ( RemoteSystemRoot < 0
        || (RemoteSystemRoot = CSafeReg::Open(
                                 (CSafeReg *)&v23,
                                 phkResult,
                                 L"SYSTEM\\CurrentControlSet\\Services\\EventLog",
                                 1u),
            RemoteSystemRoot < 0)
        || (RemoteSystemRoot = GetRemoteSystemRoot(phkResult, &v27, 0x104u), RemoteSystemRoot < 0) )
      {
        CSafeReg::Close((CSafeReg *)&v23);
        CSafeReg::Close((CSafeReg *)&phkResult);
      }
    }
    if ( **((_WORD **)this + 1) && (v7 = 0, RemoteSystemRoot >= 0)
      || (v7 = 1,
          Str = CSafeReg::Open(
                  (CSafeReg *)&v23,
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Services\\EventLog",
                  1u),
          Str >= 0) )
    {
      Str = CSafeReg::Open((CSafeReg *)&v20, v23, *((const unsigned __int16 **)this + 2), 1u);
      if ( Str >= 0 )
      {
        v21 = 0;
        Str = CSafeReg::QueryBufSize((CSafeReg *)&v20, L"Sources", &v21);
        if ( Str >= 0 )
        {
          v9 = ((unsigned __int64)v21 + 2) >> 1;
          v10 = (unsigned __int16 *)operator new[](saturated_mul(v9, 2u));
          v5 = v10;
          if ( v10 )
          {
            Str = CSafeReg::QueryStr((CSafeReg *)&v20, L"Sources", v10, v9);
            if ( Str >= 0 )
            {
              v11 = CSafeReg::QueryStr((CSafeReg *)&v20, L"PrimaryModule", &String2, 0x105u);
              v12 = v5;
              Str = 0;
              if ( v11 >= 0 )
                Str = v11;
              do
              {
                if ( !*v12 )
                  break;
                v24[0] = 0;
                if ( (int)CSafeReg::Open((CSafeReg *)v24, v20, v12, 1u) >= 0 )
                {
                  v13 = CStringArray::Add((const void **)this + 3, v12);
                  v14 = (HKEY)operator new(0x30u);
                  v24[1] = v14;
                  if ( !v14 )
                  {
                    Str = -2147024882;
                    CSafeReg::Close((CSafeReg *)v24);
                    goto LABEL_42;
                  }
                  if ( v13 && (v16 = *((_QWORD *)this + 4)) != 0 )
                    v15 = *(const WCHAR **)(v16 + 8LL * (v13 - 1));
                  else
                    v15 = &String;
                  *((_QWORD *)v14 + 1) = 0;
                  *((_QWORD *)v14 + 2) = 0;
                  *(_QWORD *)v14 = &CSourceInfo::`vftable';
                  *((_QWORD *)v14 + 3) = v15;
                  *((_DWORD *)v14 + 8) = 0;
                  *((_QWORD *)v14 + 5) = 0;
                  v17 = &String;
                  if ( !v7 )
                    v17 = (const unsigned __int16 *)*((_QWORD *)this + 1);
                  Str = CSourceInfo::Init((CSourceInfo *)v14, v24[0], v17, &v27);
                  if ( Str >= 0 )
                  {
                    v18 = (struct CDLink *)*((_QWORD *)this + 5);
                    if ( v18 )
                      CDLink::LinkAfter((CDLink *)v14, v18);
                    else
                      *((_QWORD *)this + 5) = v14;
                    if ( !*((_QWORD *)this + 6) && String2 && !lstrcmpiW(v12, &String2) )
                      *((_QWORD *)this + 6) = v14;
                  }
                  else
                  {
                    (**(void (__fastcall ***)(HKEY, __int64))v14)(v14, 1);
                  }
                }
                else
                {
                  Str = 0;
                }
                CSafeReg::Close((CSafeReg *)v24);
                v19 = -1;
                do
                  ++v19;
                while ( v12[v19] );
                v12 += v19 + 1;
              }
              while ( v12 );
              if ( Str >= 0 )
                *(_DWORD *)this = 1;
            }
          }
          else
          {
            Str = -2147024882;
          }
        }
      }
    }
LABEL_42:
    operator delete[](v5);
    if ( Str < 0 )
      CSources::Clear(this);
    *((_DWORD *)this + 1) = Str;
    CSafeReg::Close((CSafeReg *)&phkResult);
    CSafeReg::Close((CSafeReg *)&v20);
    CSafeReg::Close((CSafeReg *)&v23);
    return (unsigned int)Str;
  }
  return result;
}

```

## disassembly

```asm
0x180004b7c  push    rbp
0x180004b7e  push    rbx
0x180004b7f  push    rsi
0x180004b80  push    rdi
0x180004b81  push    r12
0x180004b83  push    r13
0x180004b85  push    r14
0x180004b87  push    r15
0x180004b89  lea     rbp, [rsp-388h]
0x180004b91  sub     rsp, 488h
0x180004b98  mov     rax, cs:__security_cookie
0x180004b9f  xor     rax, rsp
0x180004ba2  mov     [rbp+3C0h+var_50], rax
0x180004ba9  mov     rdi, rcx
0x180004bac  mov     eax, [rcx+4]
0x180004baf  xor     r13d, r13d
0x180004bb2  test    eax, eax
0x180004bb4  jnz     loc_180004EF7
0x180004bba  mov     ebx, r13d
0x180004bbd  mov     [rsp+4C0h+var_488], r13
0x180004bc2  mov     [rsp+4C0h+var_4A0], r13
0x180004bc7  mov     [rsp+4C0h+phkResult], r13
0x180004bcc  mov     [rsp+4C0h+String2], r13w
0x180004bd2  xor     edx, edx; Val
0x180004bd4  mov     r8d, 208h; Size
0x180004bda  lea     rcx, [rsp+4C0h+var_46E]; void *
0x180004bdf  call    memset_0
0x180004be4  mov     [rbp+3C0h+var_260], r13w
0x180004bec  xor     edx, edx; Val
0x180004bee  mov     r8d, 206h; Size
0x180004bf4  lea     rcx, [rbp+3C0h+var_25E]; void *
0x180004bfb  call    memset_0
0x180004c00  mov     r12d, r13d
0x180004c03  mov     rdx, [rdi+8]; lpMachineName
0x180004c07  cmp     [rdx], r13w
0x180004c0b  jz      short loc_180004C6E
0x180004c0d  lea     rcx, [rsp+4C0h+phkResult]; phkResult
0x180004c12  call    ?Connect@CSafeReg@@QEAAJPEBGPEAUHKEY__@@@Z; CSafeReg::Connect(ushort const *,HKEY__ *)
0x180004c17  mov     ebx, eax
0x180004c19  test    eax, eax
0x180004c1b  js      short loc_180004C5A
0x180004c1d  lea     r9d, [r13+1]; unsigned int
0x180004c21  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x180004c28  mov     rdx, [rsp+4C0h+phkResult]; HKEY
0x180004c2d  lea     rcx, [rsp+4C0h+var_488]; this
0x180004c32  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180004c37  mov     ebx, eax
0x180004c39  test    eax, eax
0x180004c3b  js      short loc_180004C5A
0x180004c3d  mov     r8d, 104h; unsigned int
0x180004c43  lea     rdx, [rbp+3C0h+var_260]; unsigned __int16 *
0x180004c4a  mov     rcx, [rsp+4C0h+phkResult]; HKEY
0x180004c4f  call    ?GetRemoteSystemRoot@@YAJPEAUHKEY__@@PEAGK@Z; GetRemoteSystemRoot(HKEY__ *,ushort *,ulong)
0x180004c54  mov     ebx, eax
0x180004c56  test    eax, eax
0x180004c58  jns     short loc_180004C6E
0x180004c5a  lea     rcx, [rsp+4C0h+var_488]; this
0x180004c5f  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180004c64  lea     rcx, [rsp+4C0h+phkResult]; this
0x180004c69  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180004c6e  mov     rax, [rdi+8]
0x180004c72  cmp     [rax], r13w
0x180004c76  jz      short loc_180004C7F
0x180004c78  mov     r15b, r13b
0x180004c7b  test    ebx, ebx
0x180004c7d  jns     short loc_180004CAA
0x180004c7f  mov     r15b, 1
0x180004c82  mov     r9d, 1; unsigned int
0x180004c88  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x180004c8f  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180004c96  lea     rcx, [rsp+4C0h+var_488]; this
0x180004c9b  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180004ca0  mov     ebx, eax
0x180004ca2  test    eax, eax
0x180004ca4  js      loc_180004EBD
0x180004caa  mov     r9d, 1; unsigned int
0x180004cb0  mov     r8, [rdi+10h]; unsigned __int16 *
0x180004cb4  mov     rdx, [rsp+4C0h+var_488]; HKEY
0x180004cb9  lea     rcx, [rsp+4C0h+var_4A0]; this
0x180004cbe  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180004cc3  mov     ebx, eax
0x180004cc5  test    eax, eax
0x180004cc7  js      loc_180004EBD
0x180004ccd  mov     [rsp+4C0h+var_498], r13d
0x180004cd2  lea     r8, [rsp+4C0h+var_498]; unsigned int *
0x180004cd7  lea     rdx, aSources; "Sources"
0x180004cde  lea     rcx, [rsp+4C0h+var_4A0]; this
0x180004ce3  call    ?QueryBufSize@CSafeReg@@QEAAJPEBGPEAK@Z; CSafeReg::QueryBufSize(ushort const *,ulong *)
0x180004ce8  mov     ebx, eax
0x180004cea  test    eax, eax
0x180004cec  js      loc_180004EBD
0x180004cf2  mov     ebx, [rsp+4C0h+var_498]
0x180004cf6  mov     eax, 2
0x180004cfb  add     rbx, rax
0x180004cfe  shr     rbx, 1
0x180004d01  mov     ebx, ebx
0x180004d03  mul     rbx
0x180004d06  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180004d0d  cmovb   rax, rcx
0x180004d11  mov     rcx, rax; unsigned __int64
0x180004d14  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180004d19  mov     r12, rax
0x180004d1c  test    rax, rax
0x180004d1f  jnz     short loc_180004D2B
0x180004d21  mov     ebx, 8007000Eh
0x180004d26  jmp     loc_180004EBD
0x180004d2b  mov     r9d, ebx; unsigned int
0x180004d2e  mov     r8, r12; unsigned __int16 *
0x180004d31  lea     rdx, aSources; "Sources"
0x180004d38  lea     rcx, [rsp+4C0h+var_4A0]; this
0x180004d3d  call    ?QueryStr@CSafeReg@@QEAAJPEBGPEAGK@Z; CSafeReg::QueryStr(ushort const *,ushort *,ulong)
0x180004d42  mov     ebx, eax
0x180004d44  test    eax, eax
0x180004d46  js      loc_180004EBD
0x180004d4c  mov     r9d, 105h; unsigned int
0x180004d52  lea     r8, [rsp+4C0h+String2]; unsigned __int16 *
0x180004d57  lea     rdx, aPrimarymodule; "PrimaryModule"
0x180004d5e  lea     rcx, [rsp+4C0h+var_4A0]; this
0x180004d63  call    ?QueryStr@CSafeReg@@QEAAJPEBGPEAGK@Z; CSafeReg::QueryStr(ushort const *,ushort *,ulong)
0x180004d68  mov     r14, r12
0x180004d6b  mov     ebx, r13d
0x180004d6e  test    eax, eax
0x180004d70  cmovns  ebx, eax
0x180004d73  cmp     [r14], r13w
0x180004d77  jz      loc_180004EB3
0x180004d7d  mov     [rsp+4C0h+var_480], r13
0x180004d82  mov     r9d, 1; unsigned int
0x180004d88  mov     r8, r14; unsigned __int16 *
0x180004d8b  mov     rdx, [rsp+4C0h+var_4A0]; HKEY
0x180004d90  lea     rcx, [rsp+4C0h+var_480]; this
0x180004d95  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180004d9a  test    eax, eax
0x180004d9c  jns     short loc_180004DA6
0x180004d9e  mov     ebx, r13d
0x180004da1  jmp     loc_180004E8D
0x180004da6  lea     rcx, [rdi+18h]; this
0x180004daa  mov     rdx, r14; unsigned __int16 *
0x180004dad  call    ?Add@CStringArray@@QEAAKPEBG@Z; CStringArray::Add(ushort const *)
0x180004db2  mov     ebx, eax
0x180004db4  mov     ecx, 30h ; '0'; Size
0x180004db9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004dbe  mov     rsi, rax
0x180004dc1  mov     [rsp+4C0h+var_478], rax
0x180004dc6  test    rax, rax
0x180004dc9  jz      loc_180004F1A
0x180004dcf  test    ebx, ebx
0x180004dd1  jnz     short loc_180004DDC
0x180004dd3  lea     rax, String
0x180004dda  jmp     short loc_180004DEC
0x180004ddc  mov     rdx, [rdi+20h]
0x180004de0  test    rdx, rdx
0x180004de3  jz      short loc_180004DD3
0x180004de5  lea     eax, [rbx-1]
0x180004de8  mov     rax, [rdx+rax*8]
0x180004dec  mov     [rsi+8], r13
0x180004df0  mov     [rsi+10h], r13
0x180004df4  lea     rcx, ??_7CSourceInfo@@6B@; const CSourceInfo::`vftable'
0x180004dfb  mov     [rsi], rcx
0x180004dfe  mov     [rsi+18h], rax
0x180004e02  mov     [rsi+20h], r13d
0x180004e06  mov     [rsi+28h], r13
0x180004e0a  test    rsi, rsi
0x180004e0d  jz      loc_180004F1A
0x180004e13  test    r15b, r15b
0x180004e16  lea     r8, String
0x180004e1d  jnz     short loc_180004E23
0x180004e1f  mov     r8, [rdi+8]; unsigned __int16 *
0x180004e23  lea     r9, [rbp+3C0h+var_260]; unsigned __int16 *
0x180004e2a  mov     rdx, [rsp+4C0h+var_480]; HKEY
0x180004e2f  mov     rcx, rsi; this
0x180004e32  call    ?Init@CSourceInfo@@QEAAJPEAUHKEY__@@PEBG1@Z; CSourceInfo::Init(HKEY__ *,ushort const *,ushort const *)
0x180004e37  mov     ebx, eax
0x180004e39  test    eax, eax
0x180004e3b  jns     short loc_180004E52
0x180004e3d  mov     rax, [rsi]
0x180004e40  mov     edx, 1
0x180004e45  mov     rcx, rsi
0x180004e48  mov     rax, [rax]
0x180004e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e50  jmp     short loc_180004E8D
0x180004e52  mov     rdx, [rdi+28h]; struct CDLink *
0x180004e56  test    rdx, rdx
0x180004e59  jnz     short loc_180004E61
0x180004e5b  mov     [rdi+28h], rsi
0x180004e5f  jmp     short loc_180004E69
0x180004e61  mov     rcx, rsi; this
0x180004e64  call    ?LinkAfter@CDLink@@QEAAXPEAV1@@Z; CDLink::LinkAfter(CDLink *)
0x180004e69  cmp     [rdi+30h], r13
0x180004e6d  jnz     short loc_180004E8D
0x180004e6f  cmp     [rsp+4C0h+String2], r13w
0x180004e75  jz      short loc_180004E8D
0x180004e77  lea     rdx, [rsp+4C0h+String2]; lpString2
0x180004e7c  mov     rcx, r14; lpString1
0x180004e7f  call    cs:__imp_lstrcmpiW
0x180004e85  test    eax, eax
0x180004e87  jnz     short loc_180004E8D
0x180004e89  mov     [rdi+30h], rsi
0x180004e8d  lea     rcx, [rsp+4C0h+var_480]; this
0x180004e92  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180004e97  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004e9b  inc     rax
0x180004e9e  cmp     [r14+rax*2], r13w
0x180004ea3  jnz     short loc_180004E9B
0x180004ea5  lea     r14, [r14+rax*2]
0x180004ea9  add     r14, 2
0x180004ead  jnz     loc_180004D73
0x180004eb3  test    ebx, ebx
0x180004eb5  js      short loc_180004EBD
0x180004eb7  mov     dword ptr [rdi], 1
0x180004ebd  mov     rcx, r12
0x180004ec0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004ec6  test    ebx, ebx
0x180004ec8  jns     short loc_180004ED2
0x180004eca  mov     rcx, rdi; this
0x180004ecd  call    ?Clear@CSources@@QEAAXXZ; CSources::Clear(void)
0x180004ed2  mov     [rdi+4], ebx
0x180004ed5  lea     rcx, [rsp+4C0h+phkResult]; this
0x180004eda  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180004edf  nop
0x180004ee0  lea     rcx, [rsp+4C0h+var_4A0]; this
0x180004ee5  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180004eea  nop
0x180004eeb  lea     rcx, [rsp+4C0h+var_488]; this
0x180004ef0  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180004ef5  mov     eax, ebx
0x180004ef7  mov     rcx, [rbp+3C0h+var_50]
0x180004efe  xor     rcx, rsp; StackCookie
0x180004f01  call    __security_check_cookie
0x180004f06  add     rsp, 488h
0x180004f0d  pop     r15
0x180004f0f  pop     r14
0x180004f11  pop     r13
0x180004f13  pop     r12
0x180004f15  pop     rdi
0x180004f16  pop     rsi
0x180004f17  pop     rbx
0x180004f18  pop     rbp
0x180004f19  retn
0x180004f1a  mov     ebx, 8007000Eh
0x180004f1f  lea     rcx, [rsp+4C0h+var_480]; this
0x180004f24  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180004f29  jmp     short loc_180004EBD
```
