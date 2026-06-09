# CRootPubDocFile::SwitchToFile(ushort const *,ILockBytes *,ulong *)

- ea: `0x180041970`
- end: `0x180041b0b`
- name: `?SwitchToFile@CRootPubDocFile@@QEAAJPEBGPEAUILockBytes@@PEAK@Z`
- size: `411`
- prototype: `__int64 __fastcall(CRootPubDocFile *__hidden this, const unsigned __int16 *, struct ILockBytes *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041890`

## callees

- `0x180005e68`
- `0x180007ee4`
- `0x180030c08`
- `0x1800325d4`
- `0x180034570`
- `0x180041970`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041ab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041ab9`

## pseudocode

```c
__int64 __fastcall CRootPubDocFile::SwitchToFile(
        CRootPubDocFile *this,
        const unsigned __int16 *a2,
        struct ILockBytes *a3,
        unsigned int *a4)
{
  bool v4; // zf
  __int64 v9; // rdx
  CMStream *v10; // rcx
  int CommitSize; // edi
  void *v13; // rbx
  unsigned int v14; // edx
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+30h] BYREF

  v4 = (*((_BYTE *)this + 20) & 2) == 0;
  v15 = 0;
  pv = 0;
  v18 = 0;
  if ( !v4
    || (*((_BYTE *)this + 138) & 1) == 0
    || ((v9 = *((_QWORD *)this + 18)) == 0
      ? (v10 = 0)
      : (v10 = (CMStream *)(v9 + *(_QWORD *)NtCurrentTeb()->ReservedForOle)),
        (CommitSize = CMStream::Flush(v10, 0), CommitSize >= 0)
     && (CommitSize = ((__int64 (__fastcall *)(struct ILockBytes *))a3->lpVtbl->Flush)(a3), CommitSize >= 0)) )
  {
    v17 = 0;
    CommitSize = CPubDocFile::GetCommitSize(this, &v17);
    if ( CommitSize >= 0 )
    {
      if ( ((__int64 (__fastcall *)(struct ILockBytes *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
             a3,
             &IID_IDfReserved1,
             &v15) < 0 )
        return 2147680519LL;
      if ( *a4 )
        StgpReleaseOpenLocks(a3, *((_DWORD *)this + 5), *a4);
      CommitSize = GetBuffer(0x200u, 0x10000u, (unsigned __int8 **)&pv, &v18);
      if ( CommitSize >= 0 )
      {
        v13 = pv;
        CommitSize = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int64, _QWORD, LPVOID))(*(_QWORD *)v15 + 24LL))(
                       v15,
                       a2,
                       v17,
                       v18,
                       pv);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        CoTaskMemFree(v13);
        *((_WORD *)this + 69) |= 2u;
        if ( *a4 )
        {
          v14 = *((_DWORD *)this + 5);
          v18 = 0;
          if ( (int)StgpAcquireOpenLocks(a3, v14, 0, &v18) >= 0 )
            *a4 = v18;
        }
      }
    }
  }
  return (unsigned int)CommitSize;
}

```

## disassembly

```asm
0x180041970  mov     [rsp-28h+arg_8], rbx
0x180041975  mov     [rsp-28h+arg_10], rsi
0x18004197a  push    rbp
0x18004197b  push    rdi
0x18004197c  push    r12
0x18004197e  push    r14
0x180041980  push    r15
0x180041982  mov     rbp, rsp
0x180041985  sub     rsp, 50h
0x180041989  test    byte ptr [rcx+14h], 2
0x18004198d  mov     r15, r9
0x180041990  mov     r14, r8
0x180041993  mov     [rbp+var_20], 0
0x18004199b  mov     r12, rdx
0x18004199e  mov     [rbp+pv], 0
0x1800419a6  mov     rsi, rcx
0x1800419a9  mov     [rbp+arg_0], 0
0x1800419b0  jnz     short loc_180041A0B
0x1800419b2  test    byte ptr [rcx+8Ah], 1
0x1800419b9  jz      short loc_180041A0B
0x1800419bb  mov     rdx, [rcx+90h]
0x1800419c2  test    rdx, rdx
0x1800419c5  jz      short loc_1800419DF
0x1800419c7  mov     rax, gs:30h
0x1800419d0  mov     rcx, [rax+1758h]
0x1800419d7  mov     rcx, [rcx]
0x1800419da  add     rcx, rdx
0x1800419dd  jmp     short loc_1800419E1
0x1800419df  xor     ecx, ecx; this
0x1800419e1  xor     edx, edx; int
0x1800419e3  call    ?Flush@CMStream@@QEAAJH@Z; CMStream::Flush(int)
0x1800419e8  mov     edi, eax
0x1800419ea  test    eax, eax
0x1800419ec  js      loc_180041AF0
0x1800419f2  mov     rax, [r14]
0x1800419f5  mov     rcx, r14
0x1800419f8  mov     rax, [rax+28h]
0x1800419fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a01  mov     edi, eax
0x180041a03  test    eax, eax
0x180041a05  js      loc_180041AF0
0x180041a0b  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x180041a0f  mov     [rbp+var_10], 0
0x180041a17  mov     rcx, rsi; this
0x180041a1a  call    ?GetCommitSize@CPubDocFile@@IEAAJPEA_K@Z; CPubDocFile::GetCommitSize(unsigned __int64 *)
0x180041a1f  mov     edi, eax
0x180041a21  test    eax, eax
0x180041a23  js      loc_180041AF0
0x180041a29  mov     rax, [r14]
0x180041a2c  lea     r8, [rbp+var_20]
0x180041a30  lea     rdx, IID_IDfReserved1
0x180041a37  mov     rcx, r14
0x180041a3a  mov     rax, [rax]
0x180041a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a42  test    eax, eax
0x180041a44  jns     short loc_180041A50
0x180041a46  mov     eax, 80030107h
0x180041a4b  jmp     loc_180041AF2
0x180041a50  mov     r8d, [r15]; unsigned int
0x180041a53  test    r8d, r8d
0x180041a56  jz      short loc_180041A63
0x180041a58  mov     edx, [rsi+14h]; unsigned int
0x180041a5b  mov     rcx, r14; struct ILockBytes *
0x180041a5e  call    ?StgpReleaseOpenLocks@@YAXPEAUILockBytes@@KK@Z; StgpReleaseOpenLocks(ILockBytes *,ulong,ulong)
0x180041a63  lea     r9, [rbp+arg_0]; unsigned int *
0x180041a67  mov     edx, 10000h; unsigned int
0x180041a6c  lea     r8, [rbp+pv]; unsigned __int8 **
0x180041a70  mov     ecx, 200h; unsigned int
0x180041a75  call    ?GetBuffer@@YAJKKPEAPEAEPEAK@Z; GetBuffer(ulong,ulong,uchar * *,ulong *)
0x180041a7a  mov     edi, eax
0x180041a7c  test    eax, eax
0x180041a7e  js      short loc_180041AF0
0x180041a80  mov     rcx, [rbp+var_20]
0x180041a84  mov     rdx, r12
0x180041a87  mov     rbx, [rbp+pv]
0x180041a8b  mov     r9d, [rbp+arg_0]
0x180041a8f  mov     r8, [rbp+var_10]
0x180041a93  mov     rax, [rcx]
0x180041a96  mov     [rsp+50h+var_30], rbx
0x180041a9b  mov     rax, [rax+18h]
0x180041a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041aa4  mov     rcx, [rbp+var_20]
0x180041aa8  mov     edi, eax
0x180041aaa  mov     rax, [rcx]
0x180041aad  mov     rax, [rax+10h]
0x180041ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ab6  mov     rcx, rbx; pv
0x180041ab9  call    cs:__imp_CoTaskMemFree
0x180041abf  or      word ptr [rsi+8Ah], 2
0x180041ac7  cmp     dword ptr [r15], 0
0x180041acb  jz      short loc_180041AF0
0x180041acd  mov     edx, [rsi+14h]; unsigned int
0x180041ad0  lea     r9, [rbp+arg_0]; unsigned int *
0x180041ad4  xor     r8d, r8d; int
0x180041ad7  mov     [rbp+arg_0], 0
0x180041ade  mov     rcx, r14; struct ILockBytes *
0x180041ae1  call    ?StgpAcquireOpenLocks@@YAJPEAUILockBytes@@KHPEAK@Z; StgpAcquireOpenLocks(ILockBytes *,ulong,int,ulong *)
0x180041ae6  test    eax, eax
0x180041ae8  js      short loc_180041AF0
0x180041aea  mov     eax, [rbp+arg_0]
0x180041aed  mov     [r15], eax
0x180041af0  mov     eax, edi
0x180041af2  lea     r11, [rsp+50h+var_s0]
0x180041af7  mov     rbx, [r11+38h]
0x180041afb  mov     rsi, [r11+40h]
0x180041aff  mov     rsp, r11
0x180041b02  pop     r15
0x180041b04  pop     r14
0x180041b06  pop     r12
0x180041b08  pop     rdi
0x180041b09  pop     rbp
0x180041b0a  retn
```
