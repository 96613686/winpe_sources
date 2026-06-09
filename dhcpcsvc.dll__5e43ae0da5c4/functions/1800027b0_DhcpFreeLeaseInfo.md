# DhcpFreeLeaseInfo

- ea: `0x1800027b0`
- end: `0x180002808`
- name: `DhcpFreeLeaseInfo`
- size: `88`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001240`

## callees

- `0x1800027b0`
- `0x180002810`
- `0x180002880`
- `0x180005162`
- `0x1800127f0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800027c2`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800027c2`

## pseudocode

```c
void *__fastcall DhcpFreeLeaseInfo(char *a1)
{
  LPWSTR CommandLineW; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 151, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  CleanupDNSParam(a1 + 72);
  CleanupNetBTParam(a1 + 32);
  return memset_0(a1, 0, 0x78u);
}

```

## disassembly

```asm
0x1800027b0  push    rbx
0x1800027b2  sub     rsp, 20h
0x1800027b6  mov     rbx, rcx
0x1800027b9  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800027c0  jz      short loc_1800027E1
0x1800027c2  call    cs:__imp_GetCommandLineW
0x1800027c8  mov     edx, 97h
0x1800027cd  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800027d4  mov     r9, rax
0x1800027d7  mov     ecx, 404h
0x1800027dc  call    WPP_SF_S
0x1800027e1  lea     rcx, [rbx+48h]
0x1800027e5  call    CleanupDNSParam
0x1800027ea  lea     rcx, [rbx+20h]
0x1800027ee  call    CleanupNetBTParam
0x1800027f3  xor     edx, edx; Val
0x1800027f5  mov     r8d, 78h ; 'x'; Size
0x1800027fb  mov     rcx, rbx; void *
0x1800027fe  add     rsp, 20h
0x180002802  pop     rbx
0x180002803  jmp     memset_0
```
