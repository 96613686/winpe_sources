# CGenericTableMap<unsigned __int64,CDwmHwndData>::RemoveElement(CDwmHwndData *)

- ea: `0x180005c64`
- end: `0x180005cf2`
- name: `?RemoveElement@?$CGenericTableMap@_KVCDwmHwndData@@@@QEAAXPEAVCDwmHwndData@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(PRTL_GENERIC_TABLE Table, CDwmHwndData *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001008`
- `0x180006630`

## callees

- `0x1800056c8`
- `0x180005c64`
- `0x18000d0a0`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTable` at `0x180005cbd`
- `ntdll!RtlDeleteElementGenericTable` at `0x180005cbd`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180005ccf`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180005ccf`

## pseudocode

```c
void __fastcall CGenericTableMap<unsigned __int64,CDwmHwndData>::RemoveElement(
        PRTL_GENERIC_TABLE Table,
        CDwmHwndData *this)
{
  __int64 v2; // rax
  __int64 Buffer; // [rsp+20h] [rbp-48h] BYREF
  __int128 v5; // [rsp+28h] [rbp-40h]
  __int64 v6; // [rsp+38h] [rbp-30h]
  __int64 v7; // [rsp+40h] [rbp-28h]
  __int64 v8; // [rsp+48h] [rbp-20h]
  __int64 v9; // [rsp+50h] [rbp-18h]

  v2 = *(_QWORD *)this;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  Buffer = v2;
  CDwmHwndData::~CDwmHwndData(this);
  if ( !RtlDeleteElementGenericTable(Table, &Buffer) )
    RaiseFailFastException(0, 0, 1u);
  CDwmHwndData::~CDwmHwndData((CDwmHwndData *)&Buffer);
}

```

## disassembly

```asm
0x180005c64  mov     r11, rsp
0x180005c67  push    rbx
0x180005c68  sub     rsp, 60h
0x180005c6c  mov     rax, cs:__security_cookie
0x180005c73  xor     rax, rsp
0x180005c76  mov     [rsp+68h+var_10], rax
0x180005c7b  mov     rax, [rdx]
0x180005c7e  xorps   xmm0, xmm0
0x180005c81  movups  [rsp+68h+var_40], xmm0
0x180005c86  mov     rbx, rcx
0x180005c89  mov     qword ptr [r11-30h], 0
0x180005c91  mov     rcx, rdx; this
0x180005c94  mov     qword ptr [r11-28h], 0
0x180005c9c  mov     qword ptr [r11-20h], 0
0x180005ca4  mov     qword ptr [r11-18h], 0
0x180005cac  mov     [r11-48h], rax
0x180005cb0  call    ??1CDwmHwndData@@QEAA@XZ; CDwmHwndData::~CDwmHwndData(void)
0x180005cb5  lea     rdx, [rsp+68h+Buffer]; Buffer
0x180005cba  mov     rcx, rbx; Table
0x180005cbd  call    cs:__imp_RtlDeleteElementGenericTable
0x180005cc3  test    al, al
0x180005cc5  jnz     short loc_180005CD5
0x180005cc7  xor     edx, edx; pContextRecord
0x180005cc9  xor     ecx, ecx; pExceptionRecord
0x180005ccb  lea     r8d, [rdx+1]; dwFlags
0x180005ccf  call    cs:__imp_RaiseFailFastException
0x180005cd5  lea     rcx, [rsp+68h+Buffer]; this
0x180005cda  call    ??1CDwmHwndData@@QEAA@XZ; CDwmHwndData::~CDwmHwndData(void)
0x180005cdf  mov     rcx, [rsp+68h+var_10]
0x180005ce4  xor     rcx, rsp; StackCookie
0x180005ce7  call    __security_check_cookie
0x180005cec  add     rsp, 60h
0x180005cf0  pop     rbx
0x180005cf1  retn
```
