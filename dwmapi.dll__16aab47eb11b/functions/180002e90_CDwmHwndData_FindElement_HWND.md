# CDwmHwndData::FindElement(HWND__ *)

- ea: `0x180002e90`
- end: `0x180002faf`
- name: `?FindElement@CDwmHwndData@@SAPEAV1@PEAUHWND__@@@Z`
- size: `287`
- prototype: `struct CDwmHwndData *__fastcall(HWND)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800019b0`
- `0x180002200`
- `0x180002920`

## callees

- `0x180002e90`
- `0x18000d0a0`
- `0x1800136ec`
- `0x180017010`

## import_xrefs

- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x180002f3b`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x180002f3b`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180002f29`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180002f81`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180002f29`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180002f81`
- `ntdll!RtlLookupElementGenericTable` at `0x180002ed4`
- `ntdll!RtlLookupElementGenericTable` at `0x180002ed4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f0f`

## pseudocode

```c
struct CDwmHwndData *__fastcall CDwmHwndData::FindElement(HWND a1)
{
  PVOID v1; // rbx
  _QWORD *i; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx
  PVOID RestartKey; // [rsp+20h] [rbp-58h] BYREF
  HWND v7; // [rsp+28h] [rbp-50h] BYREF
  __int128 v8; // [rsp+30h] [rbp-48h]
  HANDLE hObject; // [rsp+40h] [rbp-38h]
  __int64 v10; // [rsp+48h] [rbp-30h]
  __int64 v11; // [rsp+50h] [rbp-28h]
  PRTL_GENERIC_TABLE Table; // [rsp+58h] [rbp-20h]

  v8 = 0;
  v7 = a1;
  hObject = 0;
  v10 = 0;
  v11 = 0;
  Table = 0;
  v1 = RtlLookupElementGenericTable(&CDwmHwndData::s_dwmHwndDataMap, &v7);
  if ( hObject )
    CloseHandle(hObject);
  if ( Table )
  {
    RestartKey = 0;
    for ( i = RtlEnumerateGenericTableWithoutSplaying(Table, &RestartKey);
          i;
          i = RtlEnumerateGenericTableWithoutSplaying(Table, &RestartKey) )
    {
      i[1] = 0;
      if ( !RtlIsThreadWithinLoaderCallout() )
      {
        v4 = i[3];
        if ( v4 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          i[3] = 0;
        }
      }
      v5 = i[4];
      if ( v5 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        i[4] = 0;
      }
    }
    if ( Table )
      CGenericTableMap<unsigned __int64,CProxySurfaceElement>::`scalar deleting destructor'(Table);
  }
  return (struct CDwmHwndData *)v1;
}

```

## disassembly

```asm
0x180002e90  mov     r11, rsp
0x180002e93  mov     [r11+18h], rbx
0x180002e97  push    rsi
0x180002e98  sub     rsp, 70h
0x180002e9c  mov     rax, cs:__security_cookie
0x180002ea3  xor     rax, rsp
0x180002ea6  mov     [rsp+78h+var_18], rax
0x180002eab  xor     esi, esi
0x180002ead  lea     rdx, [r11-50h]; Buffer
0x180002eb1  xorps   xmm0, xmm0
0x180002eb4  movups  [rsp+78h+var_48], xmm0
0x180002eb9  mov     [r11-50h], rcx
0x180002ebd  lea     rcx, ?s_dwmHwndDataMap@CDwmHwndData@@0V?$CGenericTableMap@_KVCDwmHwndData@@@@A; Table
0x180002ec4  mov     [r11-38h], rsi
0x180002ec8  mov     [r11-30h], rsi
0x180002ecc  mov     [r11-28h], rsi
0x180002ed0  mov     [r11-20h], rsi
0x180002ed4  call    cs:__imp_RtlLookupElementGenericTable
0x180002eda  mov     rcx, [rsp+78h+hObject]; hObject
0x180002edf  mov     rbx, rax
0x180002ee2  test    rcx, rcx
0x180002ee5  jnz     short loc_180002F0F
0x180002ee7  mov     rcx, [rsp+78h+Table]; Table
0x180002eec  test    rcx, rcx
0x180002eef  jnz     short loc_180002F17
0x180002ef1  mov     rax, rbx
0x180002ef4  mov     rcx, [rsp+78h+var_18]
0x180002ef9  xor     rcx, rsp; StackCookie
0x180002efc  call    __security_check_cookie
0x180002f01  mov     rbx, [rsp+78h+arg_10]
0x180002f09  add     rsp, 70h
0x180002f0d  pop     rsi
0x180002f0e  retn
0x180002f0f  call    cs:__imp_CloseHandle
0x180002f15  jmp     short loc_180002EE7
0x180002f17  lea     rdx, [rsp+78h+RestartKey]; RestartKey
0x180002f1c  mov     [rsp+78h+arg_8], rdi
0x180002f24  mov     [rsp+78h+RestartKey], rsi
0x180002f29  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180002f2f  mov     rdi, rax
0x180002f32  test    rax, rax
0x180002f35  jz      short loc_180002F8F
0x180002f37  mov     [rdi+8], rsi
0x180002f3b  call    cs:__imp_RtlIsThreadWithinLoaderCallout
0x180002f41  test    al, al
0x180002f43  jnz     short loc_180002F5E
0x180002f45  mov     rcx, [rdi+18h]
0x180002f49  test    rcx, rcx
0x180002f4c  jz      short loc_180002F5E
0x180002f4e  mov     rax, [rcx]
0x180002f51  mov     rax, [rax+10h]
0x180002f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f5a  mov     [rdi+18h], rsi
0x180002f5e  mov     rcx, [rdi+20h]
0x180002f62  test    rcx, rcx
0x180002f65  jz      short loc_180002F77
0x180002f67  mov     rax, [rcx]
0x180002f6a  mov     rax, [rax+10h]
0x180002f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f73  mov     [rdi+20h], rsi
0x180002f77  mov     rcx, [rsp+78h+Table]; Table
0x180002f7c  lea     rdx, [rsp+78h+RestartKey]; RestartKey
0x180002f81  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180002f87  mov     rdi, rax
0x180002f8a  test    rax, rax
0x180002f8d  jnz     short loc_180002F37
0x180002f8f  mov     rcx, [rsp+78h+Table]; void *
0x180002f94  mov     rdi, [rsp+78h+arg_8]
0x180002f9c  test    rcx, rcx
0x180002f9f  jz      loc_180002EF1
0x180002fa5  call    ??_G?$CGenericTableMap@_KVCProxySurfaceElement@@@@QEAAPEAXI@Z; CGenericTableMap<unsigned __int64,CProxySurfaceElement>::`scalar deleting destructor'(uint)
0x180002faa  jmp     loc_180002EF1
```
