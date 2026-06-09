# SanitizeFullPath(ushort const *,ushort *)

- ea: `0x180008f10`
- end: `0x180008f87`
- name: `?SanitizeFullPath@@YAXPEBGPEAG@Z`
- size: `119`
- prototype: `void(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180008948`
- `0x180008f10`
- `0x18000e240`
- `0x1800186d4`

## string_xrefs

- `0x180008f31`: `ExePath: %ws`
- `0x180008f25`: `SanitizeFullPath`

## pseudocode

```c
void __fastcall SanitizeFullPath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  AslLogCallPrintf(3, "SanitizeFullPath", 1490, "ExePath: %ws", a1);
  if ( !dword_180026920 && (PiiFilter::Initialize((PiiFilter *)&TelemetryPiiFilter), !dword_180026920)
    || (int)PiiFilterExecute(a2) < 0 )
  {
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x180008f10  mov     [rsp+arg_0], rbx
0x180008f15  push    rdi
0x180008f16  sub     rsp, 30h
0x180008f1a  mov     rbx, rdx
0x180008f1d  mov     [rsp+38h+var_18], rcx
0x180008f22  mov     rdi, rcx
0x180008f25  lea     rdx, aSanitizefullpa_0; "SanitizeFullPath"
0x180008f2c  mov     ecx, 3
0x180008f31  lea     r9, aExepathWs; "ExePath: %ws"
0x180008f38  mov     r8d, 5D2h
0x180008f3e  call    AslLogCallPrintf
0x180008f43  cmp     cs:dword_180026920, 0
0x180008f4a  jnz     short loc_180008F61
0x180008f4c  lea     rcx, ?TelemetryPiiFilter@@3VPiiFilter@@A; this
0x180008f53  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x180008f58  cmp     cs:dword_180026920, 0
0x180008f5f  jz      short loc_180008F77
0x180008f61  mov     r8, cs:?TelemetryPiiFilter@@3VPiiFilter@@A; PiiFilter TelemetryPiiFilter
0x180008f68  mov     r9, rdi
0x180008f6b  mov     rcx, rbx; unsigned __int16 *
0x180008f6e  call    PiiFilterExecute
0x180008f73  test    eax, eax
0x180008f75  jns     short loc_180008F7C
0x180008f77  xor     eax, eax
0x180008f79  mov     [rbx], ax
0x180008f7c  mov     rbx, [rsp+38h+arg_0]
0x180008f81  add     rsp, 30h
0x180008f85  pop     rdi
0x180008f86  retn
```
