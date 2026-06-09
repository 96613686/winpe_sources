# CFtpObj::CFtpObj(void)

- ea: `0x180019774`
- end: `0x18001985e`
- name: `??0CFtpObj@@IEAA@XZ`
- size: `234`
- prototype: `CFtpObj *__fastcall(CFtpObj *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d160`
- `0x1800199e0`

## callees

- `0x180019774`
- `0x180026b34`

## import_xrefs

- `SHLWAPI!SHGetThreadRef` at `0x18001984f`
- `SHLWAPI!SHGetThreadRef` at `0x18001984f`

## pseudocode

```c
CFtpObj *__fastcall CFtpObj::CFtpObj(CFtpObj *this)
{
  HDSA v2; // rax
  unsigned int v3; // edx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // xmm1_8

  *((_DWORD *)this + 8) = 1;
  *(_QWORD *)this = &CFtpObj::`vftable'{for `IDataObject'};
  *((_QWORD *)this + 1) = &CFtpObj::`vftable'{for `IPersistStream'};
  *((_QWORD *)this + 2) = &CFtpObj::`vftable'{for `IInternetSecurityMgrSite'};
  *((_QWORD *)this + 3) = &CFtpObj::`vftable'{for `IDataObjectAsyncCapability'};
  _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 28) = -1;
  *((_DWORD *)this + 30) = 0;
  *((_DWORD *)this + 31) = 1;
  v2 = DSA_Create(72, 3);
  *((_QWORD *)this + 9) = v2;
  if ( !v2 )
    *((_DWORD *)this + 20) = 1;
  v3 = 0;
  do
  {
    v4 = (int)v3++;
    v5 = 3 * v4;
    v6 = (__int64)*(&(&c_stgInit)[3 * v4] + 2);
    *(_OWORD *)((char *)this + 8 * v5 + 152) = *(_OWORD *)&(&c_stgInit)[3 * v4];
    *((_QWORD *)this + v5 + 21) = v6;
  }
  while ( v3 < 0xD );
  if ( !*((_QWORD *)this + 18) )
    SHGetThreadRef((IUnknown **)this + 18);
  return this;
}

```

## disassembly

```asm
0x180019774  push    rbx
0x180019776  sub     rsp, 20h
0x18001977a  lea     rax, ??_7CFtpObj@@6BIDataObject@@@; const CFtpObj::`vftable'{for `IDataObject'}
0x180019781  mov     dword ptr [rcx+20h], 1
0x180019788  mov     [rcx], rax
0x18001978b  mov     rbx, rcx
0x18001978e  lea     rax, ??_7CFtpObj@@6BIPersistStream@@@; const CFtpObj::`vftable'{for `IPersistStream'}
0x180019795  mov     [rcx+8], rax
0x180019799  lea     rax, ??_7CFtpObj@@6BIInternetSecurityMgrSite@@@; const CFtpObj::`vftable'{for `IInternetSecurityMgrSite'}
0x1800197a0  mov     [rcx+10h], rax
0x1800197a4  lea     rax, ??_7CFtpObj@@6BIDataObjectAsyncCapability@@@; const CFtpObj::`vftable'{for `IDataObjectAsyncCapability'}
0x1800197ab  mov     [rcx+18h], rax
0x1800197af  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x1800197b6  mov     edx, 3; cItemGrow
0x1800197bb  mov     qword ptr [rcx+28h], 0
0x1800197c3  mov     qword ptr [rcx+30h], 0
0x1800197cb  mov     qword ptr [rcx+38h], 0
0x1800197d3  mov     qword ptr [rcx+40h], 0
0x1800197db  mov     qword ptr [rcx+58h], 0
0x1800197e3  mov     dword ptr [rcx+70h], 0FFFFFFFFh
0x1800197ea  mov     dword ptr [rcx+78h], 0
0x1800197f1  mov     dword ptr [rcx+7Ch], 1
0x1800197f8  lea     ecx, [rdx+45h]; cbItem
0x1800197fb  call    DSA_Create
0x180019800  mov     [rbx+48h], rax
0x180019804  test    rax, rax
0x180019807  jnz     short loc_180019810
0x180019809  mov     dword ptr [rbx+50h], 1
0x180019810  xor     edx, edx
0x180019812  movsxd  rax, edx
0x180019815  inc     edx
0x180019817  lea     rcx, [rax+rax*2]
0x18001981b  lea     rax, ?c_stgInit@@3PAUtagSTGMEDIUM@@A; tagSTGMEDIUM near * c_stgInit
0x180019822  movsd   xmm1, qword ptr [rax+rcx*8+10h]
0x180019828  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18001982c  movups  xmmword ptr [rbx+rcx*8+98h], xmm0
0x180019834  movsd   qword ptr [rbx+rcx*8+0A8h], xmm1
0x18001983d  cmp     edx, 0Dh
0x180019840  jb      short loc_180019812
0x180019842  lea     rcx, [rbx+90h]; ppunk
0x180019849  cmp     qword ptr [rcx], 0
0x18001984d  jnz     short loc_180019855
0x18001984f  call    cs:__imp_SHGetThreadRef
0x180019855  mov     rax, rbx
0x180019858  add     rsp, 20h
0x18001985c  pop     rbx
0x18001985d  retn
```
