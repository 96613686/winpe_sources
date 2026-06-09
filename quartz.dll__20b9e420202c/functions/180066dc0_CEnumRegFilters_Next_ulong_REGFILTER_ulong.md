# CEnumRegFilters::Next(ulong,REGFILTER * *,ulong *)

- ea: `0x180066dc0`
- end: `0x180066fe9`
- name: `?Next@CEnumRegFilters@@UEAAJKPEAPEAUREGFILTER@@PEAK@Z`
- size: `553`
- prototype: `__int64 __fastcall(CEnumRegFilters *__hidden this, unsigned int, struct REGFILTER **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180015350`
- `0x180066dc0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180066f42`
- `KERNEL32!LeaveCriticalSection` at `0x180066fd5`
- `KERNEL32!LeaveCriticalSection` at `0x180066f42`
- `KERNEL32!LeaveCriticalSection` at `0x180066fd5`
- `KERNEL32!EnterCriticalSection` at `0x180066e0e`
- `KERNEL32!EnterCriticalSection` at `0x180066e0e`
- `ole32!CoTaskMemFree` at `0x180066f72`
- `ole32!CoTaskMemFree` at `0x180066f83`
- `ole32!CoTaskMemFree` at `0x180066f9a`
- `ole32!CoTaskMemFree` at `0x180066fb8`
- `ole32!CoTaskMemFree` at `0x180066f72`
- `ole32!CoTaskMemFree` at `0x180066f83`
- `ole32!CoTaskMemFree` at `0x180066f9a`
- `ole32!CoTaskMemFree` at `0x180066fb8`
- `ole32!CoTaskMemAlloc` at `0x180066e5f`
- `ole32!CoTaskMemAlloc` at `0x180066e5f`

## pseudocode

```c
__int64 __fastcall CEnumRegFilters::Next(
        CEnumRegFilters *this,
        unsigned int a2,
        struct REGFILTER **a3,
        unsigned int *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  unsigned int v9; // edi
  unsigned int v10; // esi
  char *v11; // rax
  struct REGFILTER *v12; // r15
  int v13; // eax
  unsigned int v14; // r12d
  __int64 v15; // rax
  __int64 i; // rbp

  if ( !a3 )
    return 2147500035LL;
  v8 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 32) & -(__int64)(this != 0));
  EnterCriticalSection(v8);
  if ( *((_DWORD *)this + 38) )
  {
    if ( a4 )
      *a4 = 0;
    v9 = 1;
    goto LABEL_20;
  }
  if ( !a4 && a2 > 1 )
  {
    v9 = -2147024809;
LABEL_20:
    LeaveCriticalSection(v8);
    return v9;
  }
  v10 = 0;
  while ( 1 )
  {
    if ( v10 >= a2 )
      goto LABEL_17;
    v11 = (char *)CoTaskMemAlloc(0x220u);
    v12 = (struct REGFILTER *)v11;
    if ( !v11 )
      goto LABEL_17;
    *((_QWORD *)v11 + 2) = v11 + 24;
    v13 = CMapperCache::RegEnumFilterInfo(
            *((CMapperCache **)this + 22),
            (CEnumRegFilters *)((char *)this + 160),
            0,
            *((_DWORD *)this + 18),
            *((_DWORD *)this + 36),
            (const struct _GUID *)((char *)this + 76),
            1u,
            0,
            0,
            *((_DWORD *)this + 35),
            *((_DWORD *)this + 37),
            (const struct _GUID *)((char *)this + 108),
            1u,
            0,
            0,
            0,
            (struct _GUID *)v11,
            (unsigned __int16 *)v11 + 12);
    v14 = v13;
    if ( v13 < 0 )
    {
      CoTaskMemFree(v12);
      goto LABEL_25;
    }
    if ( v13 )
      break;
    v15 = v10++;
    a3[v15] = v12;
    if ( !*((_QWORD *)this + 20) )
    {
      *((_DWORD *)this + 38) = 1;
LABEL_17:
      if ( a4 )
        *a4 = v10;
      v9 = a2 != v10;
      goto LABEL_20;
    }
  }
  if ( v13 == 1 )
  {
    *((_DWORD *)this + 38) = 1;
    CoTaskMemFree(v12);
    goto LABEL_17;
  }
  CoTaskMemFree(v12);
  v14 = -2147418113;
LABEL_25:
  for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(i + 1) )
    CoTaskMemFree(a3[i]);
  LeaveCriticalSection(v8);
  return v14;
}

```

## disassembly

```asm
0x180066dc0  mov     [rsp+arg_10], r8
0x180066dc5  push    rbx
0x180066dc6  push    rbp
0x180066dc7  push    rsi
0x180066dc8  push    rdi
0x180066dc9  push    r12
0x180066dcb  push    r13
0x180066dcd  push    r14
0x180066dcf  push    r15
0x180066dd1  sub     rsp, 0A8h
0x180066dd8  xor     r12d, r12d
0x180066ddb  mov     r14, r9
0x180066dde  mov     r13d, edx
0x180066de1  mov     rbp, rcx
0x180066de4  test    r8, r8
0x180066de7  jnz     short loc_180066DF3
0x180066de9  mov     eax, 80004003h
0x180066dee  jmp     loc_180066F50
0x180066df3  add     rcx, 20h ; ' '
0x180066df7  mov     rax, rbp
0x180066dfa  neg     rax
0x180066dfd  sbb     rbx, rbx
0x180066e00  and     rbx, rcx
0x180066e03  mov     rcx, rbx; lpCriticalSection
0x180066e06  mov     [rsp+0E8h+var_58], rbx
0x180066e0e  call    cs:__imp_EnterCriticalSection
0x180066e15  nop     dword ptr [rax+rax+00h]
0x180066e1a  cmp     [rbp+98h], r12d
0x180066e21  jz      short loc_180066E35
0x180066e23  test    r14, r14
0x180066e26  jz      short loc_180066E2B
0x180066e28  mov     [r14], r12d
0x180066e2b  mov     edi, 1
0x180066e30  jmp     loc_180066F3F
0x180066e35  mov     edi, 1
0x180066e3a  test    r14, r14
0x180066e3d  jnz     short loc_180066E4E
0x180066e3f  cmp     r13d, edi
0x180066e42  jbe     short loc_180066E4E
0x180066e44  mov     edi, 80070057h
0x180066e49  jmp     loc_180066F3F
0x180066e4e  mov     esi, r12d
0x180066e51  cmp     esi, r13d
0x180066e54  jnb     loc_180066F2D
0x180066e5a  mov     ecx, 220h; cb
0x180066e5f  call    cs:__imp_CoTaskMemAlloc
0x180066e66  nop     dword ptr [rax+rax+00h]
0x180066e6b  mov     r15, rax
0x180066e6e  test    rax, rax
0x180066e71  jz      loc_180066F2D
0x180066e77  lea     rcx, [rax+18h]
0x180066e7b  mov     [rsp+0E8h+var_60], rcx; unsigned __int16 *
0x180066e83  lea     r8, [rbp+4Ch]
0x180066e87  mov     [rsp+0E8h+var_68], rax; struct _GUID *
0x180066e8f  lea     rdx, [rbp+6Ch]
0x180066e93  mov     [rsp+0E8h+var_70], r12; struct IMoniker **
0x180066e98  mov     [rsp+0E8h+var_78], r12; struct _GUID *
0x180066e9d  mov     [rsp+0E8h+var_80], r12; struct REGPINMEDIUM *
0x180066ea2  mov     [rsp+0E8h+var_88], edi; unsigned int
0x180066ea6  mov     [rsp+0E8h+var_90], rdx; struct _GUID *
0x180066eab  lea     rdx, [rbp+0A0h]; struct Cursor *
0x180066eb2  mov     [rax+10h], rcx
0x180066eb6  mov     eax, [rbp+94h]
0x180066ebc  mov     r9d, [rbp+48h]; unsigned int
0x180066ec0  mov     rcx, [rbp+0B0h]; this
0x180066ec7  mov     [rsp+0E8h+var_98], eax; int
0x180066ecb  mov     eax, [rbp+8Ch]
0x180066ed1  mov     [rsp+0E8h+var_A0], eax; int
0x180066ed5  mov     eax, [rbp+90h]
0x180066edb  mov     [rsp+0E8h+var_A8], r12; struct _GUID *
0x180066ee0  mov     [rsp+0E8h+var_B0], r12; struct REGPINMEDIUM *
0x180066ee5  mov     [rsp+0E8h+var_B8], edi; unsigned int
0x180066ee9  mov     [rsp+0E8h+var_C0], r8; struct _GUID *
0x180066eee  xor     r8d, r8d; bool
0x180066ef1  mov     [rsp+0E8h+var_C8], eax; int
0x180066ef5  call    ?RegEnumFilterInfo@CMapperCache@@QEAAJAEAUCursor@@_NKHPEBU_GUID@@KPEBUREGPINMEDIUM@@2HH2K32PEAPEAUIMoniker@@PEAU3@PEAG@Z; CMapperCache::RegEnumFilterInfo(Cursor &,bool,ulong,int,_GUID const *,ulong,REGPINMEDIUM const *,_GUID const *,int,int,_GUID const *,ulong,REGPINMEDIUM const *,_GUID const *,IMoniker * *,_GUID *,ushort *)
0x180066efa  mov     r12d, eax
0x180066efd  test    eax, eax
0x180066eff  js      loc_180066F97
0x180066f05  jnz     short loc_180066F65
0x180066f07  mov     rcx, [rsp+0E8h+arg_10]
0x180066f0f  xor     r12d, r12d
0x180066f12  mov     eax, esi
0x180066f14  add     esi, edi
0x180066f16  mov     [rcx+rax*8], r15
0x180066f1a  cmp     [rbp+0A0h], r12
0x180066f21  jnz     loc_180066E51
0x180066f27  mov     [rbp+98h], edi
0x180066f2d  test    r14, r14
0x180066f30  jz      short loc_180066F35
0x180066f32  mov     [r14], esi
0x180066f35  cmp     r13d, esi
0x180066f38  mov     edi, r12d
0x180066f3b  setnz   dil
0x180066f3f  mov     rcx, rbx; lpCriticalSection
0x180066f42  call    cs:__imp_LeaveCriticalSection
0x180066f49  nop     dword ptr [rax+rax+00h]
0x180066f4e  mov     eax, edi
0x180066f50  add     rsp, 0A8h
0x180066f57  pop     r15
0x180066f59  pop     r14
0x180066f5b  pop     r13
0x180066f5d  pop     r12
0x180066f5f  pop     rdi
0x180066f60  pop     rsi
0x180066f61  pop     rbp
0x180066f62  pop     rbx
0x180066f63  retn
0x180066f65  mov     rcx, r15; pv
0x180066f68  cmp     eax, edi
0x180066f6a  jnz     short loc_180066F83
0x180066f6c  mov     [rbp+98h], edi
0x180066f72  call    cs:__imp_CoTaskMemFree
0x180066f79  nop     dword ptr [rax+rax+00h]
0x180066f7e  xor     r12d, r12d
0x180066f81  jmp     short loc_180066F2D
0x180066f83  call    cs:__imp_CoTaskMemFree
0x180066f8a  nop     dword ptr [rax+rax+00h]
0x180066f8f  mov     r12d, 8000FFFFh
0x180066f95  jmp     short loc_180066FA6
0x180066f97  mov     rcx, r15; pv
0x180066f9a  call    cs:__imp_CoTaskMemFree
0x180066fa1  nop     dword ptr [rax+rax+00h]
0x180066fa6  xor     ebp, ebp
0x180066fa8  test    esi, esi
0x180066faa  jz      short loc_180066FD2
0x180066fac  mov     rbx, [rsp+0E8h+arg_10]
0x180066fb4  mov     rcx, [rbx+rbp*8]; pv
0x180066fb8  call    cs:__imp_CoTaskMemFree
0x180066fbf  nop     dword ptr [rax+rax+00h]
0x180066fc4  add     ebp, edi
0x180066fc6  cmp     ebp, esi
0x180066fc8  jb      short loc_180066FB4
0x180066fca  mov     rbx, [rsp+0E8h+var_58]
0x180066fd2  mov     rcx, rbx; lpCriticalSection
0x180066fd5  call    cs:__imp_LeaveCriticalSection
0x180066fdc  nop     dword ptr [rax+rax+00h]
0x180066fe1  mov     eax, r12d
0x180066fe4  jmp     loc_180066F50
```
