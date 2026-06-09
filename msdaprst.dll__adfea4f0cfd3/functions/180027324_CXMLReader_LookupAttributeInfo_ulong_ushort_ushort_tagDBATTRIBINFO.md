# CXMLReader::LookupAttributeInfo(ulong,ushort *,ushort *,tagDBATTRIBINFO *)

- ea: `0x180027324`
- end: `0x180027453`
- name: `?LookupAttributeInfo@CXMLReader@@AEAAJKPEAG0PEAUtagDBATTRIBINFO@@@Z`
- size: `303`
- prototype: `int(CXMLReader *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 *, struct tagDBATTRIBINFO *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800275e4`
- `0x180028148`

## callees

- `0x180027324`
- `0x180029d90`
- `0x180029dc0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18002738b`
- `OLEAUT32!__imp_SysStringLen` at `0x18002738b`

## pseudocode

```c
__int64 __fastcall CXMLReader::LookupAttributeInfo(
        CXMLReader *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct tagDBATTRIBINFO *a5)
{
  __int64 v5; // rbx
  unsigned int v9; // edi
  UINT v10; // eax
  unsigned int v11; // esi
  unsigned __int16 *v12; // r14
  int v13; // eax
  struct tagDBATTRIBINFO *v14; // rbx
  unsigned __int64 v15; // rax
  unsigned __int64 v17[9]; // [rsp+20h] [rbp-48h] BYREF
  int v18; // [rsp+78h] [rbp+10h] BYREF

  v5 = a2;
  v9 = 1;
  if ( !a2 )
    return v9;
  v18 = 6;
  v17[0] = 0;
  if ( (unsigned int)CCollectionList::LookUpByKey(
                       (CXMLReader *)((char *)this + 160),
                       a3,
                       a2,
                       (enum _NAMESPACETYPE *)&v18)
    || (unsigned int)(v18 - 2) > 1 )
  {
    return v9;
  }
  v10 = SysStringLen(a3);
  if ( v10 < (int)v5 + 1 )
    return (unsigned int)-2147024882;
  v11 = v10 - (v5 + 1);
  v12 = &a3[v5 + 1];
  v13 = CCollectionList::LookUpByKey((CXMLReader *)((char *)this + 208), v12, v11, v17);
  v14 = a5;
  if ( v13 )
  {
    if ( !(unsigned int)CCollectionList::LookUpByKey((CXMLReader *)((char *)this + 256), v12, v11, v17) )
    {
      v15 = v17[0];
      *((_DWORD *)v14 + 1) = v17[0];
      goto LABEL_13;
    }
  }
  else
  {
    v15 = v17[0];
    *((_DWORD *)a5 + 1) = v17[0];
    if ( (_DWORD)v15 != 22 )
      goto LABEL_13;
    if ( !(unsigned int)CCollectionList::LookUpByKey((CXMLReader *)((char *)this + 352), v12, v11, v17) )
    {
      v15 = v17[0];
      *(_DWORD *)v14 = v17[0];
      goto LABEL_13;
    }
  }
  v15 = v17[0];
LABEL_13:
  if ( v15 )
  {
    *((_WORD *)v14 + 4) = 8;
    v9 = 0;
    *((_QWORD *)v14 + 2) = a4;
  }
  return v9;
}

```

## disassembly

```asm
0x180027324  push    rbx
0x180027326  push    rbp
0x180027327  push    rsi
0x180027328  push    rdi
0x180027329  push    r14
0x18002732b  push    r15
0x18002732d  sub     rsp, 38h
0x180027331  mov     ebx, edx
0x180027333  mov     r15, r9
0x180027336  mov     r14, r8
0x180027339  mov     rbp, rcx
0x18002733c  mov     edi, 1
0x180027341  test    edx, edx
0x180027343  jz      loc_180027443
0x180027349  add     rcx, 0A0h; this
0x180027350  mov     [rsp+68h+arg_8], 6
0x180027358  lea     r9, [rsp+68h+arg_8]; enum _NAMESPACETYPE *
0x18002735d  mov     [rsp+68h+var_48], 0
0x180027366  mov     r8d, ebx; unsigned int
0x180027369  mov     rdx, r14; unsigned __int16 *
0x18002736c  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEAW4_NAMESPACETYPE@@@Z; CCollectionList::LookUpByKey(ushort *,ulong,_NAMESPACETYPE *)
0x180027371  test    eax, eax
0x180027373  jnz     loc_180027443
0x180027379  mov     eax, [rsp+68h+arg_8]
0x18002737d  add     eax, 0FFFFFFFEh
0x180027380  cmp     eax, edi
0x180027382  ja      loc_180027443
0x180027388  mov     rcx, r14; pbstr
0x18002738b  call    cs:__imp_SysStringLen
0x180027392  nop     dword ptr [rax+rax+00h]
0x180027397  lea     ecx, [rbx+1]
0x18002739a  mov     esi, eax
0x18002739c  cmp     eax, ecx
0x18002739e  jnb     short loc_1800273AA
0x1800273a0  mov     edi, 8007000Eh
0x1800273a5  jmp     loc_180027443
0x1800273aa  sub     esi, ecx
0x1800273ac  lea     r14, [r14+rbx*2]
0x1800273b0  add     r14, 2
0x1800273b4  lea     rcx, [rbp+0D0h]; this
0x1800273bb  mov     rdx, r14; unsigned __int16 *
0x1800273be  lea     r9, [rsp+68h+var_48]; unsigned __int64 *
0x1800273c3  mov     r8d, esi; unsigned int
0x1800273c6  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x1800273cb  mov     rbx, [rsp+68h+arg_20]
0x1800273d3  test    eax, eax
0x1800273d5  jnz     short loc_180027408
0x1800273d7  mov     rax, [rsp+68h+var_48]
0x1800273dc  mov     [rbx+4], eax
0x1800273df  cmp     eax, 16h
0x1800273e2  jnz     short loc_180027432
0x1800273e4  lea     rcx, [rbp+160h]; this
0x1800273eb  mov     r8d, esi; unsigned int
0x1800273ee  lea     r9, [rsp+68h+var_48]; unsigned __int64 *
0x1800273f3  mov     rdx, r14; unsigned __int16 *
0x1800273f6  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x1800273fb  test    eax, eax
0x1800273fd  jnz     short loc_18002742D
0x1800273ff  mov     rax, [rsp+68h+var_48]
0x180027404  mov     [rbx], eax
0x180027406  jmp     short loc_180027432
0x180027408  lea     rcx, [rbp+100h]; this
0x18002740f  mov     r8d, esi; unsigned int
0x180027412  lea     r9, [rsp+68h+var_48]; unsigned __int64 *
0x180027417  mov     rdx, r14; unsigned __int16 *
0x18002741a  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x18002741f  test    eax, eax
0x180027421  jnz     short loc_18002742D
0x180027423  mov     rax, [rsp+68h+var_48]
0x180027428  mov     [rbx+4], eax
0x18002742b  jmp     short loc_180027432
0x18002742d  mov     rax, [rsp+68h+var_48]
0x180027432  test    rax, rax
0x180027435  jz      short loc_180027443
0x180027437  mov     word ptr [rbx+8], 8
0x18002743d  xor     edi, edi
0x18002743f  mov     [rbx+10h], r15
0x180027443  mov     eax, edi
0x180027445  add     rsp, 38h
0x180027449  pop     r15
0x18002744b  pop     r14
0x18002744d  pop     rdi
0x18002744e  pop     rsi
0x18002744f  pop     rbp
0x180027450  pop     rbx
0x180027451  retn
```
