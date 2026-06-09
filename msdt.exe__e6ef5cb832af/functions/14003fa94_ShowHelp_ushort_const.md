# ShowHelp(ushort const *)

- ea: `0x14003fa94`
- end: `0x14003fb88`
- name: `?ShowHelp@@YAJPEBG@Z`
- size: `244`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000eb10`
- `0x14003516c`

## callees

- `0x140020420`
- `0x14003fa94`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14003fae6`
- `OLEAUT32!__imp_SysAllocString` at `0x14003fae6`
- `OLEAUT32!__imp_SysFreeString` at `0x14003fb6e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003fb6e`
- `ole32!CoCreateInstance` at `0x14003fac7`
- `ole32!CoCreateInstance` at `0x14003fac7`

## pseudocode

```c
__int64 __fastcall ShowHelp(OLECHAR *psz)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  OLECHAR *v4; // rdi
  int v5; // r9d
  BSTR v6; // rax
  LPVOID v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = 0;
  v2 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &v8);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 0;
    v5 = 365;
LABEL_7:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ShowHelp", v5, v2);
    goto LABEL_8;
  }
  v6 = SysAllocString(psz);
  v4 = v6;
  if ( !v6 )
  {
    v3 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ShowHelp", 368, -2147024882);
    goto LABEL_8;
  }
  v2 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v8 + 24LL))(v8, v6);
  v3 = v2;
  if ( v2 < 0 )
  {
    v5 = 371;
    goto LABEL_7;
  }
LABEL_8:
  if ( v8 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  return v3;
}

```

## disassembly

```asm
0x14003fa94  mov     r11, rsp
0x14003fa97  mov     [r11+8], rbx
0x14003fa9b  push    rdi
0x14003fa9c  sub     rsp, 30h
0x14003faa0  xor     edx, edx; pUnkOuter
0x14003faa2  mov     qword ptr [r11+10h], 0
0x14003faaa  mov     rdi, rcx
0x14003faad  lea     rax, [r11+10h]
0x14003fab1  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x14003fab8  mov     [r11-18h], rax
0x14003fabc  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x14003fac3  lea     r8d, [rdx+1]; dwClsContext
0x14003fac7  call    cs:__imp_CoCreateInstance
0x14003face  nop     dword ptr [rax+rax+00h]
0x14003fad3  mov     ebx, eax
0x14003fad5  test    eax, eax
0x14003fad7  jns     short loc_14003FAE3
0x14003fad9  xor     edi, edi
0x14003fadb  mov     r9d, 16Dh
0x14003fae1  jmp     short loc_14003FB2B
0x14003fae3  mov     rcx, rdi; psz
0x14003fae6  call    cs:__imp_SysAllocString
0x14003faed  nop     dword ptr [rax+rax+00h]
0x14003faf2  mov     rdi, rax
0x14003faf5  test    rax, rax
0x14003faf8  jnz     short loc_14003FB0B
0x14003fafa  mov     ebx, 8007000Eh
0x14003faff  mov     r9d, 170h
0x14003fb05  mov     [rsp+38h+var_18], ebx
0x14003fb09  jmp     short loc_14003FB2F
0x14003fb0b  mov     rcx, [rsp+38h+arg_8]
0x14003fb10  mov     rdx, rdi
0x14003fb13  mov     rax, [rcx]
0x14003fb16  mov     rax, [rax+18h]
0x14003fb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fb1f  mov     ebx, eax
0x14003fb21  test    eax, eax
0x14003fb23  jns     short loc_14003FB47
0x14003fb25  mov     r9d, 173h
0x14003fb2b  mov     [rsp+38h+var_18], eax
0x14003fb2f  lea     r8, aShowhelp; "ShowHelp"
0x14003fb36  mov     ecx, 1; Level
0x14003fb3b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003fb42  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003fb47  mov     rcx, [rsp+38h+arg_8]
0x14003fb4c  test    rcx, rcx
0x14003fb4f  jz      short loc_14003FB66
0x14003fb51  mov     rax, [rcx]
0x14003fb54  mov     rax, [rax+10h]
0x14003fb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fb5d  mov     [rsp+38h+arg_8], 0
0x14003fb66  test    rdi, rdi
0x14003fb69  jz      short loc_14003FB7A
0x14003fb6b  mov     rcx, rdi; bstrString
0x14003fb6e  call    cs:__imp_SysFreeString
0x14003fb75  nop     dword ptr [rax+rax+00h]
0x14003fb7a  mov     eax, ebx
0x14003fb7c  mov     rbx, [rsp+38h+arg_0]
0x14003fb81  add     rsp, 30h
0x14003fb85  pop     rdi
0x14003fb86  retn
```
