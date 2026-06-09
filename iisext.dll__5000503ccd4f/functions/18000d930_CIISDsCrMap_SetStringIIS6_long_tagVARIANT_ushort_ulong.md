# CIISDsCrMap::SetStringIIS6(long,tagVARIANT,ushort *,ulong)

- ea: `0x18000d930`
- end: `0x18000da16`
- name: `?SetStringIIS6@CIISDsCrMap@@AEAAJJUtagVARIANT@@PEAGK@Z`
- size: `230`
- prototype: `__int64 __usercall@<rax>(CIISDsCrMap *__hidden this@<rcx>, int@<edx>, struct tagVARIANT *__struct_ptr@<r8>, unsigned __int16 *@<r9>, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000d460`
- `0x18000d750`
- `0x18000d7c0`

## callees

- `0x18000a8e0`
- `0x18000cba0`
- `0x18000d210`
- `0x18000d6d8`
- `0x18000d930`
- `0x1800111e0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000d9a7`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d9a7`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::SetStringIIS6(
        CIISDsCrMap *this,
        int a2,
        struct tagVARIANT *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  __int128 v5; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  int v10; // ebx
  UINT v11; // eax
  struct tagVARIANT v13; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int16 v14[264]; // [rsp+50h] [rbp-258h] BYREF

  v5 = *(_OWORD *)&a3->vt;
  pRecInfo = a3->pRecInfo;
  v10 = CIISDsCrMap::OpenMd(this, L"Cert11/Mappings");
  if ( v10 >= 0 )
  {
    *(_OWORD *)&v13.vt = v5;
    v13.pRecInfo = pRecInfo;
    v10 = CIISDsCrMap::Locate(this, a2, &v13, v14);
    if ( v10 >= 0 )
    {
      v11 = SysStringLen(a4);
      v10 = CIISDsCrMap::SetMdData(this, v14, a5, 2, 2 * v11 + 2, (unsigned __int8 *)a4);
    }
    CIISDsCrMap::CloseMd(this, 1);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000d930  mov     rax, rsp
0x18000d933  mov     [rax+10h], rbx
0x18000d937  push    rbp
0x18000d938  push    rsi
0x18000d939  push    rdi
0x18000d93a  sub     rsp, 290h
0x18000d941  movaps  xmmword ptr [rax-28h], xmm6
0x18000d945  movaps  xmmword ptr [rax-38h], xmm7
0x18000d949  mov     rax, cs:__security_cookie
0x18000d950  xor     rax, rsp
0x18000d953  mov     [rsp+2A8h+var_48], rax
0x18000d95b  movaps  xmm6, xmmword ptr [r8]
0x18000d95f  mov     ebp, edx
0x18000d961  movsd   xmm7, qword ptr [r8+10h]
0x18000d967  lea     rdx, aCert11Mappings; "Cert11/Mappings"
0x18000d96e  mov     rsi, r9
0x18000d971  mov     rdi, rcx
0x18000d974  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000d979  mov     ebx, eax
0x18000d97b  test    eax, eax
0x18000d97d  js      short loc_18000D9E7
0x18000d97f  lea     r9, [rsp+2A8h+var_258]; unsigned __int16 *
0x18000d984  movaps  xmmword ptr [rsp+2A8h+var_278], xmm6
0x18000d989  lea     r8, [rsp+2A8h+var_278]; struct tagVARIANT
0x18000d98e  movsd   qword ptr [rsp+2A8h+var_278+10h], xmm7
0x18000d994  mov     edx, ebp; int
0x18000d996  mov     rcx, rdi; this
0x18000d999  call    ?Locate@CIISDsCrMap@@QEAAJJUtagVARIANT@@PEAG@Z; CIISDsCrMap::Locate(long,tagVARIANT,ushort *)
0x18000d99e  mov     ebx, eax
0x18000d9a0  test    eax, eax
0x18000d9a2  js      short loc_18000D9DA
0x18000d9a4  mov     rcx, rsi; pbstr
0x18000d9a7  call    cs:__imp_SysStringLen
0x18000d9ad  mov     r8d, [rsp+2A8h+arg_20]; unsigned int
0x18000d9b5  lea     rdx, [rsp+2A8h+var_258]; unsigned __int16 *
0x18000d9ba  mov     [rsp+2A8h+var_280], rsi; unsigned __int8 *
0x18000d9bf  mov     r9d, 2; unsigned int
0x18000d9c5  mov     rcx, rdi; this
0x18000d9c8  lea     eax, ds:2[rax*2]
0x18000d9cf  mov     [rsp+2A8h+var_288], eax; unsigned int
0x18000d9d3  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000d9d8  mov     ebx, eax
0x18000d9da  mov     edx, 1; int
0x18000d9df  mov     rcx, rdi; this
0x18000d9e2  call    ?CloseMd@CIISDsCrMap@@QEAAJH@Z; CIISDsCrMap::CloseMd(int)
0x18000d9e7  mov     eax, ebx
0x18000d9e9  mov     rcx, [rsp+2A8h+var_48]
0x18000d9f1  xor     rcx, rsp; StackCookie
0x18000d9f4  call    __security_check_cookie
0x18000d9f9  lea     r11, [rsp+2A8h+var_18]
0x18000da01  mov     rbx, [r11+28h]
0x18000da05  movaps  xmm6, xmmword ptr [r11-10h]
0x18000da0a  movaps  xmm7, xmmword ptr [r11-20h]
0x18000da0f  mov     rsp, r11
0x18000da12  pop     rdi
0x18000da13  pop     rsi
0x18000da14  pop     rbp
0x18000da15  retn
```
