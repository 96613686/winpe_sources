# _com_issue_errorex(long,IUnknown *,_GUID const &)

- ea: `0x14002c084`
- end: `0x14002c116`
- name: `?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z`
- size: `146`
- prototype: `void __fastcall __noreturn(int, struct IUnknown *, const struct _GUID *)`
- caller_count: `18`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400196f4`
- `0x140019a5c`
- `0x140019af4`
- `0x14001a28c`
- `0x14001b3f0`
- `0x14001b9fc`
- `0x14001c130`
- `0x14001c1b8`
- `0x14001c244`
- `0x140027534`
- `0x14002774c`
- `0x140028040`
- `0x140028454`
- `0x14002ad04`
- `0x14002ad4c`
- `0x14002ad94`
- `0x14002ae28`
- `0x14002aebc`

## callees

- `0x14002c084`
- `0x14002c238`
- `0x140030010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x14002c0f6`
- `OLEAUT32!__imp_GetErrorInfo` at `0x14002c0f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall __noreturn _com_issue_errorex(int a1, struct IUnknown *a2, const struct _GUID *a3)
{
  struct IErrorInfo *v5; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int v8; // ebx
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  IErrorInfo *pperrinfo; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  pperrinfo = 0;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v9 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a2,
           &GUID_df0b3d60_548f_101b_8e65_08002b2bd119,
           &v9) < 0
      || (v8 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *))(*(_QWORD *)v9 + 24LL))(v9, a3),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9),
          v8)
      || !GetErrorInfo(0, &pperrinfo) )
    {
      v5 = pperrinfo;
    }
    else
    {
      v5 = 0;
      pperrinfo = 0;
    }
  }
  _com_raise_error(a1, v5);
}

```

## disassembly

```asm
0x14002c084  mov     r11, rsp
0x14002c087  mov     [r11+8], rbx
0x14002c08b  push    rdi
0x14002c08c  sub     rsp, 20h
0x14002c090  mov     r9, rdx
0x14002c093  mov     rbx, r8
0x14002c096  xor     edx, edx
0x14002c098  mov     edi, ecx
0x14002c09a  mov     [r11+20h], rdx
0x14002c09e  test    r9, r9
0x14002c0a1  jz      short loc_14002C10E
0x14002c0a3  mov     rax, [r9]
0x14002c0a6  lea     r8, [r11+10h]
0x14002c0aa  mov     [r11+10h], rdx
0x14002c0ae  mov     rcx, r9
0x14002c0b1  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x14002c0b8  mov     rax, [rax]
0x14002c0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c0c0  test    eax, eax
0x14002c0c2  js      short loc_14002C109
0x14002c0c4  mov     rcx, [rsp+28h+arg_8]
0x14002c0c9  mov     rdx, rbx
0x14002c0cc  mov     rax, [rcx]
0x14002c0cf  mov     rax, [rax+18h]
0x14002c0d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c0d8  mov     rcx, [rsp+28h+arg_8]
0x14002c0dd  mov     ebx, eax
0x14002c0df  mov     rdx, [rcx]
0x14002c0e2  mov     rax, [rdx+10h]
0x14002c0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c0eb  test    ebx, ebx
0x14002c0ed  jnz     short loc_14002C109
0x14002c0ef  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x14002c0f4  xor     ecx, ecx; dwReserved
0x14002c0f6  call    cs:__imp_GetErrorInfo
0x14002c0fc  test    eax, eax
0x14002c0fe  jz      short loc_14002C109
0x14002c100  xor     edx, edx
0x14002c102  mov     [rsp+28h+pperrinfo], rdx
0x14002c107  jmp     short loc_14002C10E
0x14002c109  mov     rdx, [rsp+28h+pperrinfo]; struct IErrorInfo *
0x14002c10e  mov     ecx, edi; int
0x14002c110  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
