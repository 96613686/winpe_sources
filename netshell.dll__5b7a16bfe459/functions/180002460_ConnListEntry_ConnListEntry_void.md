# ConnListEntry::~ConnListEntry(void)

- ea: `0x180002460`
- end: `0x18000258f`
- name: `??1ConnListEntry@@QEAA@XZ`
- size: `303`
- prototype: `void __fastcall(ConnListEntry *__hidden this)`
- caller_count: `40`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800022f0`
- `0x180003770`
- `0x1800049e0`
- `0x180004f10`
- `0x180008060`
- `0x180009388`
- `0x180015864`
- `0x180016bfc`
- `0x180016eb4`
- `0x180018f74`
- `0x18001d0bc`
- `0x18001d188`
- `0x180041968`
- `0x180041cf8`
- `0x180041fb4`
- `0x18004205c`
- `0x1800421c0`
- `0x180042294`
- `0x1800424fc`
- `0x1800426a4`
- `0x180042fb4`
- `0x180048470`
- `0x18004abf0`
- `0x18004ae40`
- `0x18004b060`
- `0x18004b674`
- `0x18004bb40`
- `0x1800622a3`
- `0x180062450`
- `0x180062510`
- `0x180062550`
- `0x180062670`
- `0x180062690`
- `0x1800628d4`
- `0x180062b46`
- `0x180062e70`
- `0x180063932`
- `0x180063ad0`
- `0x180063bb9`
- `0x180064014`

## callees

- `0x180002460`

## import_xrefs

- `SHELL32!__imp_SHFree` at `0x1800024b9`
- `SHELL32!__imp_SHFree` at `0x1800024cc`
- `SHELL32!__imp_SHFree` at `0x1800024df`
- `SHELL32!__imp_SHFree` at `0x1800024f2`
- `SHELL32!__imp_SHFree` at `0x180002505`
- `SHELL32!__imp_SHFree` at `0x180002545`
- `SHELL32!__imp_SHFree` at `0x18000255e`
- `SHELL32!__imp_SHFree` at `0x180002577`
- `SHELL32!__imp_SHFree` at `0x1800024b9`
- `SHELL32!__imp_SHFree` at `0x1800024cc`
- `SHELL32!__imp_SHFree` at `0x1800024df`
- `SHELL32!__imp_SHFree` at `0x1800024f2`
- `SHELL32!__imp_SHFree` at `0x180002505`
- `SHELL32!__imp_SHFree` at `0x180002545`
- `SHELL32!__imp_SHFree` at `0x18000255e`
- `SHELL32!__imp_SHFree` at `0x180002577`
- `ole32!CoTaskMemFree` at `0x18000247e`
- `ole32!CoTaskMemFree` at `0x18000248f`
- `ole32!CoTaskMemFree` at `0x18000249c`
- `ole32!CoTaskMemFree` at `0x18000247e`
- `ole32!CoTaskMemFree` at `0x18000248f`
- `ole32!CoTaskMemFree` at `0x18000249c`

## pseudocode

```c
void __fastcall ConnListEntry::~ConnListEntry(ConnListEntry *this)
{
  LPVOID *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  v2 = (LPVOID *)*((_QWORD *)this + 19);
  if ( v2 )
  {
    CoTaskMemFree(*v2);
    CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 19) + 8LL));
    CoTaskMemFree(*((LPVOID *)this + 19));
    *((_QWORD *)this + 19) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 9);
  *((_DWORD *)this + 30) = 1;
  if ( v3 )
  {
    SHFree(v3);
    *((_QWORD *)this + 9) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 10);
  if ( v4 )
  {
    SHFree(v4);
    *((_QWORD *)this + 10) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 14);
  if ( v5 )
  {
    SHFree(v5);
    *((_QWORD *)this + 14) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
  {
    SHFree(v6);
    *((_QWORD *)this + 11) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 12);
  if ( v7 )
  {
    SHFree(v7);
    *((_QWORD *)this + 12) = 0;
    *((_DWORD *)this + 26) = 0;
  }
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 16) = 0;
  *((GUID *)this + 2) = GUID_NULL;
  *(_QWORD *)((char *)this + 20) = 0;
  *((_DWORD *)this + 7) = 0;
  *((GUID *)this + 3) = GUID_NULL;
  v8 = (void *)*((_QWORD *)this + 18);
  if ( v8 )
    SHFree(v8);
  *((_QWORD *)this + 18) = 0;
  v9 = (void *)*((_QWORD *)this + 17);
  if ( v9 )
    SHFree(v9);
  *((_QWORD *)this + 17) = 0;
  v10 = (void *)*((_QWORD *)this + 16);
  if ( v10 )
    SHFree(v10);
  *((_QWORD *)this + 16) = 0;
}

```

## disassembly

```asm
0x180002460  mov     [rsp+arg_0], rbx
0x180002465  push    rdi
0x180002466  sub     rsp, 20h
0x18000246a  mov     rbx, rcx
0x18000246d  xor     edi, edi
0x18000246f  mov     rcx, [rcx+98h]
0x180002476  test    rcx, rcx
0x180002479  jz      short loc_1800024A9
0x18000247b  mov     rcx, [rcx]; pv
0x18000247e  call    cs:__imp_CoTaskMemFree
0x180002484  mov     rcx, [rbx+98h]
0x18000248b  mov     rcx, [rcx+8]; pv
0x18000248f  call    cs:__imp_CoTaskMemFree
0x180002495  mov     rcx, [rbx+98h]; pv
0x18000249c  call    cs:__imp_CoTaskMemFree
0x1800024a2  mov     [rbx+98h], rdi
0x1800024a9  mov     rcx, [rbx+48h]; pv
0x1800024ad  mov     dword ptr [rbx+78h], 1
0x1800024b4  test    rcx, rcx
0x1800024b7  jz      short loc_1800024C3
0x1800024b9  call    cs:__imp_SHFree
0x1800024bf  mov     [rbx+48h], rdi
0x1800024c3  mov     rcx, [rbx+50h]; pv
0x1800024c7  test    rcx, rcx
0x1800024ca  jz      short loc_1800024D6
0x1800024cc  call    cs:__imp_SHFree
0x1800024d2  mov     [rbx+50h], rdi
0x1800024d6  mov     rcx, [rbx+70h]; pv
0x1800024da  test    rcx, rcx
0x1800024dd  jz      short loc_1800024E9
0x1800024df  call    cs:__imp_SHFree
0x1800024e5  mov     [rbx+70h], rdi
0x1800024e9  mov     rcx, [rbx+58h]; pv
0x1800024ed  test    rcx, rcx
0x1800024f0  jz      short loc_1800024FC
0x1800024f2  call    cs:__imp_SHFree
0x1800024f8  mov     [rbx+58h], rdi
0x1800024fc  mov     rcx, [rbx+60h]; pv
0x180002500  test    rcx, rcx
0x180002503  jz      short loc_180002512
0x180002505  call    cs:__imp_SHFree
0x18000250b  mov     [rbx+60h], rdi
0x18000250f  mov     [rbx+68h], edi
0x180002512  mov     [rbx+8], rdi
0x180002516  mov     [rbx+10h], edi
0x180002519  mov     [rbx+40h], edi
0x18000251c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180002523  movups  xmmword ptr [rbx+20h], xmm0
0x180002527  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18000252e  mov     [rbx+14h], rdi
0x180002532  mov     [rbx+1Ch], edi
0x180002535  movups  xmmword ptr [rbx+30h], xmm1
0x180002539  mov     rcx, [rbx+90h]; pv
0x180002540  test    rcx, rcx
0x180002543  jz      short loc_18000254B
0x180002545  call    cs:__imp_SHFree
0x18000254b  mov     [rbx+90h], rdi
0x180002552  mov     rcx, [rbx+88h]; pv
0x180002559  test    rcx, rcx
0x18000255c  jz      short loc_180002564
0x18000255e  call    cs:__imp_SHFree
0x180002564  mov     [rbx+88h], rdi
0x18000256b  mov     rcx, [rbx+80h]; pv
0x180002572  test    rcx, rcx
0x180002575  jz      short loc_18000257D
0x180002577  call    cs:__imp_SHFree
0x18000257d  mov     [rbx+80h], rdi
0x180002584  mov     rbx, [rsp+28h+arg_0]
0x180002589  add     rsp, 20h
0x18000258d  pop     rdi
0x18000258e  retn
```
