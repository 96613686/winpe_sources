# CGenericTableMap<unsigned __int64,CDwmHwndData>::FindElement(unsigned __int64)

- ea: `0x1800061c0`
- end: `0x1800062df`
- name: `?FindElement@?$CGenericTableMap@_KVCDwmHwndData@@@@QEAAPEAVCDwmHwndData@@_K@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001008`

## callees

- `0x1800061c0`
- `0x18000d0a0`
- `0x1800136ec`
- `0x180017010`

## import_xrefs

- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x18000626b`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x18000626b`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180006259`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800062b1`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180006259`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800062b1`
- `ntdll!RtlLookupElementGenericTable` at `0x180006204`
- `ntdll!RtlLookupElementGenericTable` at `0x180006204`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000623f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000623f`

## pseudocode

```c
PVOID __fastcall CGenericTableMap<unsigned __int64,CDwmHwndData>::FindElement(__int64 a1, __int64 a2)
{
  PVOID v2; // rbx
  _QWORD *i; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  PVOID RestartKey; // [rsp+20h] [rbp-58h] BYREF
  __int64 v8; // [rsp+28h] [rbp-50h] BYREF
  __int128 v9; // [rsp+30h] [rbp-48h]
  HANDLE hObject; // [rsp+40h] [rbp-38h]
  __int64 v11; // [rsp+48h] [rbp-30h]
  __int64 v12; // [rsp+50h] [rbp-28h]
  PRTL_GENERIC_TABLE Table; // [rsp+58h] [rbp-20h]

  v9 = 0;
  v8 = a2;
  hObject = 0;
  v11 = 0;
  v12 = 0;
  Table = 0;
  v2 = RtlLookupElementGenericTable(&CDwmHwndData::s_dwmHwndDataMap, &v8);
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
        v5 = i[3];
        if ( v5 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          i[3] = 0;
        }
      }
      v6 = i[4];
      if ( v6 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        i[4] = 0;
      }
    }
    if ( Table )
      CGenericTableMap<unsigned __int64,CProxySurfaceElement>::`scalar deleting destructor'(Table);
  }
  return v2;
}

```

## disassembly

```asm
0x1800061c0  mov     r11, rsp
0x1800061c3  mov     [r11+18h], rbx
0x1800061c7  push    rsi
0x1800061c8  sub     rsp, 70h
0x1800061cc  mov     rax, cs:__security_cookie
0x1800061d3  xor     rax, rsp
0x1800061d6  mov     [rsp+78h+var_18], rax
0x1800061db  xor     esi, esi
0x1800061dd  lea     rcx, ?s_dwmHwndDataMap@CDwmHwndData@@0V?$CGenericTableMap@_KVCDwmHwndData@@@@A; Table
0x1800061e4  xorps   xmm0, xmm0
0x1800061e7  movups  [rsp+78h+var_48], xmm0
0x1800061ec  mov     [r11-50h], rdx
0x1800061f0  lea     rdx, [r11-50h]; Buffer
0x1800061f4  mov     [r11-38h], rsi
0x1800061f8  mov     [r11-30h], rsi
0x1800061fc  mov     [r11-28h], rsi
0x180006200  mov     [r11-20h], rsi
0x180006204  call    cs:__imp_RtlLookupElementGenericTable
0x18000620a  mov     rcx, [rsp+78h+hObject]; hObject
0x18000620f  mov     rbx, rax
0x180006212  test    rcx, rcx
0x180006215  jnz     short loc_18000623F
0x180006217  mov     rcx, [rsp+78h+Table]; Table
0x18000621c  test    rcx, rcx
0x18000621f  jnz     short loc_180006247
0x180006221  mov     rax, rbx
0x180006224  mov     rcx, [rsp+78h+var_18]
0x180006229  xor     rcx, rsp; StackCookie
0x18000622c  call    __security_check_cookie
0x180006231  mov     rbx, [rsp+78h+arg_10]
0x180006239  add     rsp, 70h
0x18000623d  pop     rsi
0x18000623e  retn
0x18000623f  call    cs:__imp_CloseHandle
0x180006245  jmp     short loc_180006217
0x180006247  lea     rdx, [rsp+78h+RestartKey]; RestartKey
0x18000624c  mov     [rsp+78h+arg_0], rdi
0x180006254  mov     [rsp+78h+RestartKey], rsi
0x180006259  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x18000625f  mov     rdi, rax
0x180006262  test    rax, rax
0x180006265  jz      short loc_1800062BF
0x180006267  mov     [rdi+8], rsi
0x18000626b  call    cs:__imp_RtlIsThreadWithinLoaderCallout
0x180006271  test    al, al
0x180006273  jnz     short loc_18000628E
0x180006275  mov     rcx, [rdi+18h]
0x180006279  test    rcx, rcx
0x18000627c  jz      short loc_18000628E
0x18000627e  mov     rax, [rcx]
0x180006281  mov     rax, [rax+10h]
0x180006285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000628a  mov     [rdi+18h], rsi
0x18000628e  mov     rcx, [rdi+20h]
0x180006292  test    rcx, rcx
0x180006295  jz      short loc_1800062A7
0x180006297  mov     rax, [rcx]
0x18000629a  mov     rax, [rax+10h]
0x18000629e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a3  mov     [rdi+20h], rsi
0x1800062a7  mov     rcx, [rsp+78h+Table]; Table
0x1800062ac  lea     rdx, [rsp+78h+RestartKey]; RestartKey
0x1800062b1  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x1800062b7  mov     rdi, rax
0x1800062ba  test    rax, rax
0x1800062bd  jnz     short loc_180006267
0x1800062bf  mov     rcx, [rsp+78h+Table]; void *
0x1800062c4  mov     rdi, [rsp+78h+arg_0]
0x1800062cc  test    rcx, rcx
0x1800062cf  jz      loc_180006221
0x1800062d5  call    ??_G?$CGenericTableMap@_KVCProxySurfaceElement@@@@QEAAPEAXI@Z; CGenericTableMap<unsigned __int64,CProxySurfaceElement>::`scalar deleting destructor'(uint)
0x1800062da  jmp     loc_180006221
```
