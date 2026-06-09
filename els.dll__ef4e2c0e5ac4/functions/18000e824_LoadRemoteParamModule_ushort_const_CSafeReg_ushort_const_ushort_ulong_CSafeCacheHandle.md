# LoadRemoteParamModule(ushort const *,CSafeReg *,ushort const *,ushort *,ulong,CSafeCacheHandle *)

- ea: `0x18000e824`
- end: `0x18000e900`
- name: `?LoadRemoteParamModule@@YA?AW4MODULE_LOAD_STATUS@@PEBGPEAVCSafeReg@@0PEAGKPEAVCSafeCacheHandle@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(wchar_t *, CSafeReg *, const unsigned __int16 *, wchar_t *, __int64, struct CSafeCacheHandle *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000f09c`

## callees

- `0x18000c368`
- `0x18000e824`
- `0x18001af3c`
- `0x18001f084`
- `0x18001f3a4`
- `0x180022292`
- `0x1800222d0`

## pseudocode

```c
__int64 __fastcall LoadRemoteParamModule(
        wchar_t *a1,
        CSafeReg *a2,
        const unsigned __int16 *a3,
        wchar_t *a4,
        __int64 a5,
        struct CSafeCacheHandle *a6)
{
  int v10; // eax
  CDllCache *v11; // rcx
  wchar_t Source; // [rsp+30h] [rbp-248h] BYREF
  _BYTE v14[526]; // [rsp+32h] [rbp-246h] BYREF

  Source = 0;
  memset_0(v14, 0, 0x208u);
  if ( *(_QWORD *)a2 )
  {
    v10 = CSafeReg::QueryPath(a2, L"ParameterMessageFile", &Source, 0x105u, 0);
    if ( v10 >= 0 )
    {
      v10 = ExpandRemoteSystemRoot(&Source, a3, a4, 0x105u);
      if ( v10 >= 0 )
      {
        ConvertPathToUNC(a1, a4, 0x105u);
        v10 = CDllCache::Fetch(v11, a4, a6);
      }
    }
  }
  else
  {
    v10 = -2147467259;
  }
  return ((v10 >> 31) & 1u) + 1;
}

```

## disassembly

```asm
0x18000e824  push    rbx
0x18000e826  push    rbp
0x18000e827  push    rsi
0x18000e828  push    rdi
0x18000e829  push    r14
0x18000e82b  sub     rsp, 250h
0x18000e832  mov     rax, cs:__security_cookie
0x18000e839  xor     rax, rsp
0x18000e83c  mov     [rsp+278h+var_38], rax
0x18000e844  mov     r14, [rsp+278h+arg_28]
0x18000e84c  mov     rsi, r8
0x18000e84f  mov     rdi, rdx
0x18000e852  mov     rbp, rcx
0x18000e855  xor     eax, eax
0x18000e857  lea     rcx, [rsp+278h+var_246]; void *
0x18000e85c  xor     edx, edx; Val
0x18000e85e  mov     [rsp+278h+Source], ax
0x18000e863  mov     r8d, 208h; Size
0x18000e869  mov     rbx, r9
0x18000e86c  call    memset_0
0x18000e871  cmp     qword ptr [rdi], 0
0x18000e875  jnz     short loc_18000E87E
0x18000e877  mov     eax, 80004005h
0x18000e87c  jmp     short loc_18000E8DA
0x18000e87e  mov     r9d, 105h; unsigned int
0x18000e884  mov     [rsp+278h+var_258], 0; int
0x18000e88c  lea     r8, [rsp+278h+Source]; unsigned __int16 *
0x18000e891  mov     rcx, rdi; this
0x18000e894  lea     rdx, aParametermessa; "ParameterMessageFile"
0x18000e89b  call    ?QueryPath@CSafeReg@@QEAAJPEBGPEAGKH@Z; CSafeReg::QueryPath(ushort const *,ushort *,ulong,int)
0x18000e8a0  test    eax, eax
0x18000e8a2  js      short loc_18000E8DA
0x18000e8a4  mov     r9d, 105h; SizeInWords
0x18000e8aa  lea     rcx, [rsp+278h+Source]; Source
0x18000e8af  mov     r8, rbx; Destination
0x18000e8b2  mov     rdx, rsi; Src
0x18000e8b5  call    ?ExpandRemoteSystemRoot@@YAJPEAGPEBG0K@Z; ExpandRemoteSystemRoot(ushort *,ushort const *,ushort *,ulong)
0x18000e8ba  test    eax, eax
0x18000e8bc  js      short loc_18000E8DA
0x18000e8be  mov     r8d, 105h; SizeInWords
0x18000e8c4  mov     rdx, rbx; Destination
0x18000e8c7  mov     rcx, rbp; Source
0x18000e8ca  call    ?ConvertPathToUNC@@YAJPEBGPEAGK@Z; ConvertPathToUNC(ushort const *,ushort *,ulong)
0x18000e8cf  mov     r8, r14; struct CSafeCacheHandle *
0x18000e8d2  mov     rdx, rbx; unsigned __int16 *
0x18000e8d5  call    ?Fetch@CDllCache@@QEAAJPEBGPEAVCSafeCacheHandle@@@Z; CDllCache::Fetch(ushort const *,CSafeCacheHandle *)
0x18000e8da  sar     eax, 1Fh
0x18000e8dd  and     eax, 1
0x18000e8e0  inc     eax
0x18000e8e2  mov     rcx, [rsp+278h+var_38]
0x18000e8ea  xor     rcx, rsp; StackCookie
0x18000e8ed  call    __security_check_cookie
0x18000e8f2  add     rsp, 250h
0x18000e8f9  pop     r14
0x18000e8fb  pop     rdi
0x18000e8fc  pop     rsi
0x18000e8fd  pop     rbp
0x18000e8fe  pop     rbx
0x18000e8ff  retn
```
