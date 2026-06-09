# CNDFHelperClass::SetRootData(ushort const *,HKEY__ *,ushort const *,ushort const *)

- ea: `0x180010564`
- end: `0x18001063b`
- name: `?SetRootData@CNDFHelperClass@@QEAAJPEBGPEAUHKEY__@@00@Z`
- size: `215`
- prototype: `int(CNDFHelperClass *__hidden this, const unsigned __int16 *, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007d5c`

## callees

- `0x180010564`
- `0x180010684`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001060d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001060d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010621`

## pseudocode

```c
__int64 __fastcall CNDFHelperClass::SetRootData(
        LPVOID *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v8; // esi
  const unsigned __int16 *v9; // r8
  void *v10; // rbx
  const unsigned __int16 *v11; // r8
  void *v12; // rdi
  LPVOID pv[7]; // [rsp+30h] [rbp-38h] BYREF

  pv[0] = 0;
  v8 = UtilAssembleStringsWithAlloc((unsigned __int16 **)pv, 0xFFFFu, a3, a2);
  if ( v8 >= 0 )
  {
    v10 = pv[0];
    pv[0] = 0;
    v8 = UtilAssembleStringsWithAlloc((unsigned __int16 **)pv, 0xFFFFu, v9, a4);
    if ( v8 >= 0 )
    {
      v12 = pv[0];
      pv[0] = 0;
      v8 = UtilAssembleStringsWithAlloc((unsigned __int16 **)pv, 0xFFFFu, v11, a5);
      if ( v8 >= 0 )
      {
        this[2] = pv[0];
        this[1] = v10;
        this[3] = v12;
        this[4] = (LPVOID)a3;
        return (unsigned int)v8;
      }
      if ( v12 )
        CoTaskMemFree(v12);
    }
    if ( v10 )
      CoTaskMemFree(v10);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010564  push    rbx
0x180010566  push    rbp
0x180010567  push    rsi
0x180010568  push    rdi
0x180010569  push    r14
0x18001056b  sub     rsp, 40h
0x18001056f  mov     rdi, r9
0x180010572  mov     [rsp+68h+pv], 0
0x18001057b  mov     r9, rdx; unsigned __int16 *
0x18001057e  mov     rbp, rcx
0x180010581  mov     edx, 0FFFFh; unsigned int
0x180010586  lea     rcx, [rsp+68h+pv]; unsigned __int16 **
0x18001058b  mov     r14, r8
0x18001058e  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x180010593  mov     esi, eax
0x180010595  test    eax, eax
0x180010597  js      loc_18001062D
0x18001059d  mov     rbx, [rsp+68h+pv]
0x1800105a2  lea     rcx, [rsp+68h+pv]; unsigned __int16 **
0x1800105a7  mov     r9, rdi; unsigned __int16 *
0x1800105aa  mov     [rsp+68h+pv], 0
0x1800105b3  mov     edx, 0FFFFh; unsigned int
0x1800105b8  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x1800105bd  mov     esi, eax
0x1800105bf  test    eax, eax
0x1800105c1  js      short loc_180010619
0x1800105c3  mov     rdi, [rsp+68h+pv]
0x1800105c8  lea     rcx, [rsp+68h+pv]; unsigned __int16 **
0x1800105cd  mov     r9, [rsp+68h+arg_20]; unsigned __int16 *
0x1800105d5  mov     edx, 0FFFFh; unsigned int
0x1800105da  mov     [rsp+68h+pv], 0
0x1800105e3  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x1800105e8  mov     esi, eax
0x1800105ea  test    eax, eax
0x1800105ec  js      short loc_180010605
0x1800105ee  mov     rax, [rsp+68h+pv]
0x1800105f3  mov     [rbp+10h], rax
0x1800105f7  mov     [rbp+8], rbx
0x1800105fb  mov     [rbp+18h], rdi
0x1800105ff  mov     [rbp+20h], r14
0x180010603  jmp     short loc_18001062D
0x180010605  test    rdi, rdi
0x180010608  jz      short loc_180010619
0x18001060a  mov     rcx, rdi; pv
0x18001060d  call    cs:__imp_CoTaskMemFree
0x180010614  nop     dword ptr [rax+rax+00h]
0x180010619  test    rbx, rbx
0x18001061c  jz      short loc_18001062D
0x18001061e  mov     rcx, rbx; pv
0x180010621  call    cs:__imp_CoTaskMemFree
0x180010628  nop     dword ptr [rax+rax+00h]
0x18001062d  mov     eax, esi
0x18001062f  add     rsp, 40h
0x180010633  pop     r14
0x180010635  pop     rdi
0x180010636  pop     rsi
0x180010637  pop     rbp
0x180010638  pop     rbx
0x180010639  retn
```
