# CReadMap::_SetUpResidue(ulong)

- ea: `0x18000d2f0`
- end: `0x18000d3e3`
- name: `?_SetUpResidue@CReadMap@@AEAAXK@Z`
- size: `243`
- prototype: `void __fastcall(CReadMap *this, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180002bf0`
- `0x180007d7c`
- `0x18000d160`

## callees

- `0x180005b64`
- `0x18000aa50`
- `0x18000b974`
- `0x18000d2f0`
- `0x18001266c`

## pseudocode

```c
void __fastcall CReadMap::_SetUpResidue(CReadMap *this, unsigned int a2)
{
  unsigned int v2; // r8d
  unsigned int v4; // edx
  CBuffer *v6; // rax
  int v7; // edx
  int v8; // edx
  CBuffer *v9; // rcx
  struct _RECORDPAGE *FirstPage; // rax
  unsigned int v11; // ecx
  __int64 v12; // rdx
  unsigned int pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  v2 = *((_DWORD *)this + 46);
  *((_DWORD *)this + 6) = v2;
  v4 = *(_DWORD *)this & -v2;
  *((_DWORD *)this + 5) = v4;
  v6 = CLogStorage::_MapBuffer(*((CLogStorage **)this + 22), v4, v2, 1, 0);
  *((_QWORD *)this + 4) = v6;
  *((_DWORD *)this + 11) = 1;
  if ( !a2 )
    a2 = **((_DWORD **)this + 22);
  if ( !CBuffer::GetFirstPage(v6, v7, a2, 0, 0)
    && !(unsigned int)CLogStorage::SetLastPage(
                        *((CLogStorage **)this + 22),
                        a2,
                        *((_DWORD *)this + 5),
                        *((struct CBuffer **)this + 4)) )
  {
    pExceptionObject = -2147479510;
    throw &pExceptionObject;
  }
  v9 = (CBuffer *)*((_QWORD *)this + 4);
  pExceptionObject = 0;
  FirstPage = CBuffer::GetFirstPage(v9, v8, a2, &pExceptionObject, 0);
  v11 = pExceptionObject;
  v12 = (unsigned int)(*(_DWORD *)this - *((_DWORD *)this + 5) - 32);
  *((_DWORD *)this + 3) = v12;
  *((_DWORD *)this + 4) = 24;
  *((_DWORD *)this + 7) = v11;
  *((_DWORD *)this + 1) = *(_DWORD *)((char *)FirstPage + v12 + 40);
}

```

## disassembly

```asm
0x18000d2f0  mov     [rsp+arg_0], rbx
0x18000d2f5  push    rdi
0x18000d2f6  sub     rsp, 30h
0x18000d2fa  mov     r8d, [rcx+0B8h]; unsigned int
0x18000d301  mov     edi, edx
0x18000d303  mov     edx, r8d
0x18000d306  mov     [rcx+18h], r8d
0x18000d30a  neg     edx
0x18000d30c  mov     dword ptr [rsp+38h+var_18], 0; unsigned int
0x18000d314  and     edx, [rcx]; unsigned int
0x18000d316  mov     rbx, rcx
0x18000d319  mov     [rcx+14h], edx
0x18000d31c  mov     r9d, 1; int
0x18000d322  mov     rcx, [rcx+0B0h]; this
0x18000d329  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000d32e  mov     [rbx+20h], rax
0x18000d332  mov     rcx, rax; this
0x18000d335  mov     dword ptr [rbx+2Ch], 1
0x18000d33c  test    edi, edi
0x18000d33e  jnz     short loc_18000D349
0x18000d340  mov     rax, [rbx+0B0h]
0x18000d347  mov     edi, [rax]
0x18000d349  xor     r9d, r9d; unsigned int *
0x18000d34c  mov     [rsp+38h+var_18], 0; unsigned int *
0x18000d355  mov     r8d, edi; unsigned int
0x18000d358  call    ?GetFirstPage@CBuffer@@QEAAPEAU_RECORDPAGE@@HKPEAK0@Z; CBuffer::GetFirstPage(int,ulong,ulong *,ulong *)
0x18000d35d  test    rax, rax
0x18000d360  jnz     short loc_18000D37C
0x18000d362  mov     r9, [rbx+20h]; struct CBuffer *
0x18000d366  mov     edx, edi; unsigned int
0x18000d368  mov     r8d, [rbx+14h]; unsigned int
0x18000d36c  mov     rcx, [rbx+0B0h]; this
0x18000d373  call    ?SetLastPage@CLogStorage@@QEAAHKKPEAVCBuffer@@@Z; CLogStorage::SetLastPage(ulong,ulong,CBuffer *)
0x18000d378  test    eax, eax
0x18000d37a  jz      short loc_18000D3C9
0x18000d37c  mov     rcx, [rbx+20h]; this
0x18000d380  lea     r9, [rsp+38h+pExceptionObject]; unsigned int *
0x18000d385  mov     r8d, edi; unsigned int
0x18000d388  mov     [rsp+38h+pExceptionObject], 0
0x18000d390  mov     [rsp+38h+var_18], 0; unsigned int *
0x18000d399  call    ?GetFirstPage@CBuffer@@QEAAPEAU_RECORDPAGE@@HKPEAK0@Z; CBuffer::GetFirstPage(int,ulong,ulong *,ulong *)
0x18000d39e  mov     edx, [rbx]
0x18000d3a0  sub     edx, [rbx+14h]
0x18000d3a3  mov     ecx, [rsp+38h+pExceptionObject]
0x18000d3a7  add     edx, 0FFFFFFE0h
0x18000d3aa  mov     [rbx+0Ch], edx
0x18000d3ad  mov     dword ptr [rbx+10h], 18h
0x18000d3b4  mov     [rbx+1Ch], ecx
0x18000d3b7  mov     eax, [rdx+rax+28h]
0x18000d3bb  mov     [rbx+4], eax
0x18000d3be  mov     rbx, [rsp+38h+arg_0]
0x18000d3c3  add     rsp, 30h
0x18000d3c7  pop     rdi
0x18000d3c8  retn
0x18000d3c9  lea     rdx, _TI1K; pThrowInfo
0x18000d3d0  mov     [rsp+38h+pExceptionObject], 8000102Ah
0x18000d3d8  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000d3dd  call    _CxxThrowException_0
```
