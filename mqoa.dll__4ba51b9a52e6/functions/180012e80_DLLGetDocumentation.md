# DLLGetDocumentation

- ea: `0x180012e80`
- end: `0x180012ec0`
- name: `DLLGetDocumentation`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180012e80`
- `0x180026ac8`

## string_xrefs

- `0x180012ea2`: `MQUTIL.DLL`

## pseudocode

```c
__int64 __fastcall DLLGetDocumentation(__int64 a1, __int64 a2, __int64 a3, UINT a4, wchar_t **a5)
{
  if ( !a5 )
    return 2147500035LL;
  *a5 = 0;
  return !GetMessageOfId(a4, L"MQUTIL.DLL", 0, a5) ? 0x8002802B : 0;
}

```

## disassembly

```asm
0x180012e80  sub     rsp, 28h
0x180012e84  mov     eax, r9d
0x180012e87  mov     r9, [rsp+28h+arg_20]; wchar_t **
0x180012e8c  test    r9, r9
0x180012e8f  jnz     short loc_180012E98
0x180012e91  mov     eax, 80004003h
0x180012e96  jmp     short loc_180012EBB
0x180012e98  xor     r8d, r8d; int
0x180012e9b  mov     qword ptr [r9], 0
0x180012ea2  lea     rdx, aMqutilDll; "MQUTIL.DLL"
0x180012ea9  mov     ecx, eax; uID
0x180012eab  call    ?GetMessageOfId@@YAHKPEA_WHPEAPEA_W@Z; GetMessageOfId(ulong,wchar_t *,int,wchar_t * *)
0x180012eb0  neg     eax
0x180012eb2  sbb     eax, eax
0x180012eb4  not     eax
0x180012eb6  and     eax, 8002802Bh
0x180012ebb  add     rsp, 28h
0x180012ebf  retn
```
