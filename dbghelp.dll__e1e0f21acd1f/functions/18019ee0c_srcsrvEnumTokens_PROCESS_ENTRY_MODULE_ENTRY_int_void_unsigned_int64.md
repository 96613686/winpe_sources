# srcsrvEnumTokens(_PROCESS_ENTRY *,_MODULE_ENTRY *,int (*)(void *,unsigned __int64))

- ea: `0x18019ee0c`
- end: `0x18019eed7`
- name: `?srcsrvEnumTokens@@YAHPEAU_PROCESS_ENTRY@@PEAU_MODULE_ENTRY@@P6AHPEAX_K@Z@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct _PROCESS_ENTRY *, struct _MODULE_ENTRY *, int (*)(void *, unsigned __int64))`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801a5a40`

## callees

- `0x18000dfac`
- `0x180021374`
- `0x18019ee0c`
- `0x18019f648`
- `0x180205010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ee5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ee5e`

## string_xrefs

- `0x18019eea8`: `Error 0x%x enumerating source tokens in %s\n`

## pseudocode

```c
__int64 __fastcall srcsrvEnumTokens(
        struct _PROCESS_ENTRY *a1,
        struct _MODULE_ENTRY *a2,
        int (*a3)(void *, unsigned __int64))
{
  __int64 v7; // r8
  __int16 v8; // ax

  if ( srcsrvLoadModule(a1, a2, 0, 0) )
  {
    if ( qword_1802AF9A8 && (unsigned int)qword_1802AF9A8(*((_QWORD *)a1 + 6), *((_QWORD *)a2 + 3), a3) )
      return 1;
  }
  else
  {
    GetLastError();
    if ( (unsigned int)spew() )
    {
      v8 = *((_WORD *)a2 + 87);
      if ( (_DWORD)v7 == 232 )
        _pwprint(a1, L"%s is not source indexed\n", (char *)a2 + (v8 != 0 ? 174LL : 46LL));
      else
        _pwprint(a1, L"Error 0x%x enumerating source tokens in %s\n", v7, (char *)a2 + (v8 != 0 ? 174LL : 46LL));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18019ee0c  mov     [rsp+arg_0], rbx
0x18019ee11  mov     [rsp+arg_8], rsi
0x18019ee16  push    rdi
0x18019ee17  sub     rsp, 20h
0x18019ee1b  mov     rsi, r8
0x18019ee1e  xor     r9d, r9d; unsigned __int64
0x18019ee21  xor     r8d, r8d; unsigned __int8 *
0x18019ee24  mov     rbx, rdx
0x18019ee27  mov     rdi, rcx
0x18019ee2a  call    ?srcsrvLoadModule@@YAHPEAU_PROCESS_ENTRY@@PEAU_MODULE_ENTRY@@PEAE_K@Z; srcsrvLoadModule(_PROCESS_ENTRY *,_MODULE_ENTRY *,uchar *,unsigned __int64)
0x18019ee2f  test    eax, eax
0x18019ee31  jz      short loc_18019EE5E
0x18019ee33  mov     rax, cs:qword_1802AF9A8
0x18019ee3a  test    rax, rax
0x18019ee3d  jz      loc_18019EEC5
0x18019ee43  mov     rdx, [rbx+18h]
0x18019ee47  mov     r8, rsi
0x18019ee4a  mov     rcx, [rdi+30h]
0x18019ee4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ee53  test    eax, eax
0x18019ee55  jz      short loc_18019EEC5
0x18019ee57  mov     eax, 1
0x18019ee5c  jmp     short loc_18019EEC7
0x18019ee5e  call    cs:__imp_GetLastError
0x18019ee64  mov     r8d, eax
0x18019ee67  call    ?spew@@YAHXZ; spew(void)
0x18019ee6c  test    eax, eax
0x18019ee6e  jz      short loc_18019EEC5
0x18019ee70  movzx   eax, word ptr [rbx+0AEh]
0x18019ee77  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18019ee7a  cmp     r8d, 0E8h
0x18019ee81  jnz     short loc_18019EEA5
0x18019ee83  neg     ax
0x18019ee86  lea     rdx, aSIsNotSourceIn; "%s is not source indexed\n"
0x18019ee8d  sbb     r8, r8
0x18019ee90  and     r8d, 80h
0x18019ee97  add     r8, 2Eh ; '.'
0x18019ee9b  add     r8, rbx
0x18019ee9e  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18019eea3  jmp     short loc_18019EEC5
0x18019eea5  neg     ax
0x18019eea8  lea     rdx, aError0xXEnumer; "Error 0x%x enumerating source tokens in"...
0x18019eeaf  sbb     r9, r9
0x18019eeb2  and     r9d, 80h
0x18019eeb9  add     r9, 2Eh ; '.'
0x18019eebd  add     r9, rbx
0x18019eec0  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18019eec5  xor     eax, eax
0x18019eec7  mov     rbx, [rsp+28h+arg_0]
0x18019eecc  mov     rsi, [rsp+28h+arg_8]
0x18019eed1  add     rsp, 20h
0x18019eed5  pop     rdi
0x18019eed6  retn
```
