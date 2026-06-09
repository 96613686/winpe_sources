# CUSTOM_PROVIDERS_CONFIG_ELEMENT::InitializeSingleProvider(IAppHostElement *)

- ea: `0x18004693c`
- end: `0x180046b3f`
- name: `?InitializeSingleProvider@CUSTOM_PROVIDERS_CONFIG_ELEMENT@@IEAAJPEAUIAppHostElement@@@Z`
- size: `515`
- prototype: `int(CUSTOM_PROVIDERS_CONFIG_ELEMENT *__hidden this, struct IAppHostElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180044c20`

## callees

- `0x180001210`
- `0x180001250`
- `0x180001814`
- `0x18002afc4`
- `0x18002b5bc`
- `0x18004693c`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180046af9`
- `OLEAUT32!__imp_SysFreeString` at `0x180046af9`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180046a07`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180046a07`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046a9a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046aad`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046ac6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046a9a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046aad`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046ac6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUSTOM_PROVIDERS_CONFIG_ELEMENT::InitializeSingleProvider(
        CUSTOM_PROVIDERS_CONFIG_ELEMENT *this,
        struct IAppHostElement *a2)
{
  __int64 v4; // r14
  volatile signed __int32 *v5; // rsi
  void (__fastcall ***v6)(_QWORD, __int64); // r8
  signed int BoolProperty; // ebx
  int Key; // eax
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  volatile signed __int32 *v11; // r14
  const unsigned __int16 *v12; // r13
  const unsigned __int16 *v13; // r12
  volatile signed __int32 *v15; // [rsp+70h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+50h] BYREF

  LODWORD(v15) = 0;
  v4 = (**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer);
  bstrString = 0;
  v5 = 0;
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v6 )
  {
    if ( *(v6 - 1) )
      (**v6)(*((_QWORD *)this + 2), 3);
    else
      operator delete(v6 - 1);
    *((_QWORD *)this + 2) = 0;
    *((_DWORD *)this + 2) = 0;
  }
  BoolProperty = Config_GetBoolProperty(a2, L"enabled", (int *)&v15);
  if ( BoolProperty >= 0 )
  {
    if ( (_DWORD)v15 )
    {
      BoolProperty = Config_GetStringProperty(a2, L"name", &bstrString);
      if ( BoolProperty >= 0 )
      {
        v15 = 0;
        Key = CLKRHashTable::FindKey(v4 + 200, bstrString, &v15);
        v5 = v15;
        if ( Key )
        {
          BoolProperty = Key != 2 ? 0x80004005 : 0;
          goto LABEL_23;
        }
        v9 = operator new(0x260u);
        v15 = (volatile signed __int32 *)v9;
        if ( v9 )
        {
          *v9 = 1;
          v10 = v9 + 1;
          `eh vector constructor iterator'(
            v9 + 1,
            0x258u,
            1,
            (void (*)(void *))CUSTOM_PROVIDER_ENTRY::CUSTOM_PROVIDER_ENTRY,
            (void (*)(void *))CUSTOM_PROVIDER_ENTRY::~CUSTOM_PROVIDER_ENTRY);
        }
        else
        {
          v10 = 0;
        }
        *((_QWORD *)this + 2) = v10;
        if ( !v10 )
        {
          BoolProperty = -2147024888;
          goto LABEL_23;
        }
        v11 = (volatile signed __int32 *)*((_QWORD *)v5 + 2);
        v12 = (const unsigned __int16 *)*((_QWORD *)v5 + 33);
        v13 = (const unsigned __int16 *)*((_QWORD *)v5 + 18);
        BoolProperty = STRU::Copy((STRU *)(v10 + 3), *((const unsigned __int16 **)v5 + 7));
        if ( BoolProperty >= 0
          && (BoolProperty = STRU::Copy((STRU *)(v10 + 14), v13), BoolProperty >= 0)
          && (BoolProperty = STRU::Copy((STRU *)(v10 + 29), v12), BoolProperty >= 0)
          && v11 )
        {
          _InterlockedIncrement(v11);
          v10[2] = v11;
        }
        else if ( BoolProperty < 0 )
        {
          goto LABEL_23;
        }
        *((_DWORD *)this + 2) = 1;
      }
    }
  }
LABEL_23:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v5 && _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v5)(v5, 1);
  return (unsigned int)BoolProperty;
}

```

## disassembly

```asm
0x18004693c  mov     [rsp-38h+arg_8], rbx
0x180046941  push    rbp
0x180046942  push    rsi
0x180046943  push    rdi
0x180046944  push    r12
0x180046946  push    r13
0x180046948  push    r14
0x18004694a  push    r15
0x18004694c  mov     rbp, rsp
0x18004694f  sub     rsp, 30h
0x180046953  mov     rdi, rdx
0x180046956  mov     r15, rcx
0x180046959  xor     r12d, r12d
0x18004695c  mov     dword ptr [rbp+arg_0], r12d
0x180046960  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180046967  mov     rax, [rcx]
0x18004696a  mov     rax, [rax]
0x18004696d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046972  mov     r14, rax
0x180046975  mov     [rbp+bstrString], r12
0x180046979  mov     esi, r12d
0x18004697c  mov     r8, [r15+10h]
0x180046980  test    r8, r8
0x180046983  jz      short loc_1800469B0
0x180046985  lea     rcx, [r8-8]; Block
0x180046989  cmp     [rcx], r12
0x18004698c  jz      short loc_1800469A3
0x18004698e  mov     rdx, [r8]
0x180046991  mov     rax, [rdx]
0x180046994  lea     edx, [r12+3]
0x180046999  mov     rcx, r8
0x18004699c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469a1  jmp     short loc_1800469A8
0x1800469a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800469a8  mov     [r15+10h], r12
0x1800469ac  mov     [r15+8], r12d
0x1800469b0  lea     r8, [rbp+arg_0]; int *
0x1800469b4  lea     rdx, aEnabled; "enabled"
0x1800469bb  mov     rcx, rdi; struct IAppHostElement *
0x1800469be  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x1800469c3  mov     ebx, eax
0x1800469c5  test    eax, eax
0x1800469c7  js      loc_180046AF0
0x1800469cd  cmp     dword ptr [rbp+arg_0], r12d
0x1800469d1  jz      loc_180046AF0
0x1800469d7  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x1800469db  lea     rdx, aName; "name"
0x1800469e2  mov     rcx, rdi; struct IAppHostElement *
0x1800469e5  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x1800469ea  mov     ebx, eax
0x1800469ec  test    eax, eax
0x1800469ee  js      loc_180046AF0
0x1800469f4  mov     [rbp+arg_0], r12
0x1800469f8  lea     rcx, [r14+0C8h]
0x1800469ff  lea     r8, [rbp+arg_0]
0x180046a03  mov     rdx, [rbp+bstrString]
0x180046a07  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180046a0d  mov     rsi, [rbp+arg_0]
0x180046a11  test    eax, eax
0x180046a13  jz      short loc_180046A27
0x180046a15  sub     eax, 2
0x180046a18  neg     eax
0x180046a1a  sbb     ebx, ebx
0x180046a1c  and     ebx, 80004005h
0x180046a22  jmp     loc_180046AF0
0x180046a27  mov     ecx, 260h; Size
0x180046a2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046a31  mov     [rbp+arg_0], rax
0x180046a35  test    rax, rax
0x180046a38  jz      short loc_180046A6D
0x180046a3a  mov     qword ptr [rax], 1
0x180046a41  lea     rdi, [rax+8]
0x180046a45  lea     rax, ??1CUSTOM_PROVIDER_ENTRY@@UEAA@XZ; CUSTOM_PROVIDER_ENTRY::~CUSTOM_PROVIDER_ENTRY(void)
0x180046a4c  mov     [rsp+30h+var_10], rax; void (*)(void *)
0x180046a51  lea     r9, ??0CUSTOM_PROVIDER_ENTRY@@QEAA@XZ; void (*)(void *)
0x180046a58  mov     edx, 258h; unsigned __int64
0x180046a5d  mov     r8d, 1; unsigned __int64
0x180046a63  mov     rcx, rdi; void *
0x180046a66  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180046a6b  jmp     short loc_180046A70
0x180046a6d  mov     rdi, r12
0x180046a70  mov     [r15+10h], rdi
0x180046a74  test    rdi, rdi
0x180046a77  jnz     short loc_180046A80
0x180046a79  mov     ebx, 80070008h
0x180046a7e  jmp     short loc_180046AF0
0x180046a80  mov     r14, [rsi+10h]
0x180046a84  mov     r13, [rsi+108h]
0x180046a8b  mov     r12, [rsi+90h]
0x180046a92  lea     rcx, [rdi+18h]
0x180046a96  mov     rdx, [rsi+38h]
0x180046a9a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180046aa0  mov     ebx, eax
0x180046aa2  test    eax, eax
0x180046aa4  js      short loc_180046AE1
0x180046aa6  lea     rcx, [rdi+70h]
0x180046aaa  mov     rdx, r12
0x180046aad  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180046ab3  mov     ebx, eax
0x180046ab5  xor     r12d, r12d
0x180046ab8  test    eax, eax
0x180046aba  js      short loc_180046AE4
0x180046abc  lea     rcx, [rdi+0E8h]
0x180046ac3  mov     rdx, r13
0x180046ac6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180046acc  mov     ebx, eax
0x180046ace  test    eax, eax
0x180046ad0  js      short loc_180046AE4
0x180046ad2  test    r14, r14
0x180046ad5  jz      short loc_180046AE4
0x180046ad7  lock inc dword ptr [r14]
0x180046adb  mov     [rdi+10h], r14
0x180046adf  jmp     short loc_180046AE8
0x180046ae1  xor     r12d, r12d
0x180046ae4  test    ebx, ebx
0x180046ae6  js      short loc_180046AF0
0x180046ae8  mov     dword ptr [r15+8], 1
0x180046af0  mov     rcx, [rbp+bstrString]; bstrString
0x180046af4  test    rcx, rcx
0x180046af7  jz      short loc_180046B03
0x180046af9  call    cs:__imp_SysFreeString
0x180046aff  mov     [rbp+bstrString], r12
0x180046b03  test    rsi, rsi
0x180046b06  jz      short loc_180046B28
0x180046b08  or      eax, 0FFFFFFFFh
0x180046b0b  lock xadd [rsi+0Ch], eax
0x180046b10  cmp     eax, 1
0x180046b13  jnz     short loc_180046B28
0x180046b15  mov     rax, [rsi]
0x180046b18  mov     edx, 1
0x180046b1d  mov     rcx, rsi
0x180046b20  mov     rax, [rax]
0x180046b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b28  mov     eax, ebx
0x180046b2a  mov     rbx, [rsp+30h+arg_8]
0x180046b2f  add     rsp, 30h
0x180046b33  pop     r15
0x180046b35  pop     r14
0x180046b37  pop     r13
0x180046b39  pop     r12
0x180046b3b  pop     rdi
0x180046b3c  pop     rsi
0x180046b3d  pop     rbp
0x180046b3e  retn
```
