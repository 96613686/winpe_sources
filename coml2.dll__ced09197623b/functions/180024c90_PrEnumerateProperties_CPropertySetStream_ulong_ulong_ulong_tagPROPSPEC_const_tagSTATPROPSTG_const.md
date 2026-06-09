# PrEnumerateProperties(CPropertySetStream *,ulong,ulong *,ulong *,tagPROPSPEC * const,tagSTATPROPSTG * const)

- ea: `0x180024c90`
- end: `0x180024fc5`
- name: `?PrEnumerateProperties@@YAJPEAVCPropertySetStream@@KPEAK1QEAUtagPROPSPEC@@QEAUtagSTATPROPSTG@@@Z`
- size: `821`
- prototype: `__int64 __usercall@<rax>(struct CPropertySetStream *this@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, unsigned int *@<r9>, struct tagPROPSPEC *const, struct tagSTATPROPSTG *const)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024bac`

## callees

- `0x180024c90`
- `0x1800269c0`
- `0x180026b1c`
- `0x180028f78`
- `0x180028fa8`
- `0x180029c28`
- `0x18003dd0c`
- `0x180042800`
- `0x180043100`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024ef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024ef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024d01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ebf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024d01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ebf`

## pseudocode

```c
__int64 __fastcall PrEnumerateProperties(
        struct CPropertySetStream *this,
        int a2,
        unsigned int *a3,
        unsigned int *a4,
        struct tagPROPSPEC *const a5,
        struct tagSTATPROPSTG *const a6)
{
  void *v6; // rdi
  __int64 v7; // r13
  unsigned int *v8; // rbx
  __int64 result; // rax
  unsigned int v13; // eax
  int v14; // edx
  unsigned int v15; // ecx
  struct tagSTATPROPSTG *v16; // r12
  unsigned __int8 v17; // al
  unsigned int v18; // edx
  struct tagSERIALIZEDPROPERTYVALUE *v19; // rax
  unsigned __int16 *v20; // rax
  __int64 v21; // rsi
  unsigned int v22; // ebx
  int v23; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int8 v24; // [rsp+34h] [rbp-75h]
  unsigned int v25; // [rsp+38h] [rbp-71h] BYREF
  unsigned int *v26; // [rsp+40h] [rbp-69h]
  LPVOID pv; // [rsp+48h] [rbp-61h] BYREF
  int v28; // [rsp+50h] [rbp-59h]
  unsigned int v29; // [rsp+54h] [rbp-55h]
  char v30; // [rsp+60h] [rbp-49h] BYREF

  v6 = 0;
  v7 = *a4;
  v8 = 0;
  v28 = a2;
  v23 = 0;
  pv = 0;
  if ( a6 )
    memset_0(a6, 0, 16 * v7);
  v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5), 0);
  if ( v23 >= 0 )
  {
    v26 = 0;
    v13 = CPropertySetStream::ReOpen(this, &v23);
    v14 = v23;
    v25 = v13;
    if ( v23 < 0 )
      goto LABEL_29;
    if ( v13 > (unsigned int)v7 )
    {
      v25 = v7;
      v13 = v7;
    }
    v23 = 0;
    if ( !a6 )
      goto LABEL_10;
    if ( v13 <= 0x14 )
    {
      v8 = (unsigned int *)&v30;
    }
    else
    {
      v26 = (unsigned int *)CoTaskMemAlloc(4LL * v13);
      v8 = v26;
      if ( !v26 )
      {
        v14 = -1073741670;
        v23 = -1073741670;
LABEL_29:
        v23 = Unlock(this, v14);
        if ( v6 )
          CoTaskMemFree(v6);
        goto LABEL_4;
      }
    }
LABEL_10:
    CPropertySetStream::EnumeratePropids(this, a3, &v25, v8, &v23);
    v14 = v23;
    if ( v23 >= 0 )
    {
      v15 = v25;
      *a4 = v25;
      if ( v8 )
      {
        v16 = a6;
        while ( 1 )
        {
          v29 = v15 - 1;
          if ( !v15 )
            break;
          v25 = 0;
          if ( (v28 & 1) != 0 )
          {
            v24 = 0;
          }
          else
          {
            v17 = CPropertySetStream::QueryPropertyNames(this, 1u, v8, (unsigned __int16 **const)&pv, &v23);
            v14 = v23;
            v6 = pv;
            v24 = v17;
            if ( v23 < 0 )
              goto LABEL_28;
          }
          if ( v16 )
          {
            if ( (*((_BYTE *)this + 19) & 0x40) != 0 )
            {
              v14 = -1073741790;
              goto LABEL_39;
            }
            v18 = *v8;
            if ( !*v8 )
            {
              v14 = -1073741811;
              goto LABEL_39;
            }
            if ( v18 + 0x7FFFFFFF <= 1 )
            {
              v14 = -1073741637;
              goto LABEL_39;
            }
            v19 = CPropertySetStream::_LoadProperty(this, v18, &v25, &v23);
            v14 = v23;
            if ( v23 < 0 )
              v19 = 0;
            pv = v19;
            if ( v23 < 0 )
              goto LABEL_28;
            if ( v24 )
            {
              v20 = CPropertySetStream::DuplicatePropertyName(this, (const unsigned __int16 *)v6, &v23);
              v14 = v23;
              v16->lpwstrName = v20;
              if ( v14 < 0 )
                goto LABEL_28;
            }
            v16->propid = *v8;
            v16->vt = *(_WORD *)pv;
            ++v16;
          }
          ++v8;
          CoTaskMemFree(v6);
          v15 = v29;
          v6 = 0;
          pv = 0;
        }
      }
      v14 = 0;
LABEL_39:
      v23 = v14;
    }
LABEL_28:
    v8 = v26;
    goto LABEL_29;
  }
LABEL_4:
  CoTaskMemFree(v8);
  result = (unsigned int)v23;
  if ( v23 < 0 )
  {
    if ( a6 )
    {
      v21 = *((_QWORD *)this + 4);
      v22 = 0;
      if ( (_DWORD)v7 )
      {
        do
        {
          if ( a6[v22].lpwstrName )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
            a6[v22].lpwstrName = 0;
          }
          ++v22;
        }
        while ( v22 < (unsigned int)v7 );
        return (unsigned int)v23;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024c90  mov     [rsp-8+arg_8], rbx
0x180024c95  push    rbp
0x180024c96  push    rsi
0x180024c97  push    rdi
0x180024c98  push    r12
0x180024c9a  push    r13
0x180024c9c  push    r14
0x180024c9e  push    r15
0x180024ca0  lea     rbp, [rsp-17h]
0x180024ca5  sub     rsp, 0C0h
0x180024cac  mov     rax, cs:__security_cookie
0x180024cb3  xor     rax, rsp
0x180024cb6  mov     [rbp+47h+var_40], rax
0x180024cba  mov     r15, [rbp+47h+arg_28]
0x180024cbe  xor     edi, edi
0x180024cc0  mov     r13d, [r9]
0x180024cc3  xor     ebx, ebx
0x180024cc5  mov     [rbp+47h+var_A0], edx
0x180024cc8  mov     r14, r9
0x180024ccb  mov     [rbp+47h+var_C0], 0
0x180024cd2  mov     r12, r8
0x180024cd5  mov     [rbp+47h+pv], rdi
0x180024cd9  mov     rsi, rcx
0x180024cdc  test    r15, r15
0x180024cdf  jnz     loc_180024ECA
0x180024ce5  mov     rcx, [rsi+28h]
0x180024ce9  xor     edx, edx
0x180024ceb  mov     rax, [rcx]
0x180024cee  mov     rax, [rax+58h]
0x180024cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cf7  mov     [rbp+47h+var_C0], eax
0x180024cfa  test    eax, eax
0x180024cfc  jns     short loc_180024D39
0x180024cfe  mov     rcx, rbx; pv
0x180024d01  call    cs:__imp_CoTaskMemFree
0x180024d07  mov     eax, [rbp+47h+var_C0]
0x180024d0a  test    eax, eax
0x180024d0c  js      loc_180024F79
0x180024d12  mov     rcx, [rbp+47h+var_40]
0x180024d16  xor     rcx, rsp; StackCookie
0x180024d19  call    __security_check_cookie
0x180024d1e  mov     rbx, [rsp+0F0h+arg_8]
0x180024d26  add     rsp, 0C0h
0x180024d2d  pop     r15
0x180024d2f  pop     r14
0x180024d31  pop     r13
0x180024d33  pop     r12
0x180024d35  pop     rdi
0x180024d36  pop     rsi
0x180024d37  pop     rbp
0x180024d38  retn
0x180024d39  lea     rdx, [rbp+47h+var_C0]; int *
0x180024d3d  mov     [rbp+47h+var_B0], rbx
0x180024d41  mov     rcx, rsi; this
0x180024d44  call    ?ReOpen@CPropertySetStream@@QEAAKPEAJ@Z; CPropertySetStream::ReOpen(long *)
0x180024d49  mov     edx, [rbp+47h+var_C0]
0x180024d4c  mov     [rbp+47h+var_B8], eax
0x180024d4f  test    edx, edx
0x180024d51  js      loc_180024EA8
0x180024d57  cmp     eax, r13d
0x180024d5a  ja      loc_180024EE0
0x180024d60  mov     [rbp+47h+var_C0], ebx
0x180024d63  test    r15, r15
0x180024d66  jnz     loc_180024EEC
0x180024d6c  lea     rax, [rbp+47h+var_C0]
0x180024d70  mov     r9, rbx; unsigned int *
0x180024d73  lea     r8, [rbp+47h+var_B8]; unsigned int *
0x180024d77  mov     [rsp+0F0h+var_D0], rax; int *
0x180024d7c  mov     rdx, r12; unsigned int *
0x180024d7f  mov     rcx, rsi; this
0x180024d82  call    ?EnumeratePropids@CPropertySetStream@@QEAAEPEAK00PEAJ@Z; CPropertySetStream::EnumeratePropids(ulong *,ulong *,ulong *,long *)
0x180024d87  mov     edx, [rbp+47h+var_C0]; int
0x180024d8a  test    edx, edx
0x180024d8c  js      loc_180024EA4
0x180024d92  mov     ecx, [rbp+47h+var_B8]
0x180024d95  mov     [r14], ecx
0x180024d98  test    rbx, rbx
0x180024d9b  jz      loc_180024F6F
0x180024da1  mov     r12, r15
0x180024da4  xor     r14d, r14d
0x180024da7  mov     eax, ecx
0x180024da9  dec     ecx
0x180024dab  mov     [rbp+47h+var_9C], ecx
0x180024dae  test    eax, eax
0x180024db0  jz      loc_180024F6F
0x180024db6  test    byte ptr [rbp+47h+var_A0], 1
0x180024dba  mov     [rbp+47h+var_B8], 0
0x180024dc1  jnz     loc_180024E9A
0x180024dc7  lea     rax, [rbp+47h+var_C0]
0x180024dcb  mov     r8, rbx; unsigned int *
0x180024dce  lea     r9, [rbp+47h+pv]; unsigned __int16 **
0x180024dd2  mov     [rsp+0F0h+var_D0], rax; int *
0x180024dd7  mov     edx, 1; unsigned int
0x180024ddc  mov     rcx, rsi; this
0x180024ddf  call    ?QueryPropertyNames@CPropertySetStream@@QEAAEKPEBKQEAPEAGPEAJ@Z; CPropertySetStream::QueryPropertyNames(ulong,ulong const *,ushort * * const,long *)
0x180024de4  mov     edx, [rbp+47h+var_C0]
0x180024de7  mov     rdi, [rbp+47h+pv]
0x180024deb  mov     [rbp+47h+var_BC], al
0x180024dee  test    edx, edx
0x180024df0  js      loc_180024EA4
0x180024df6  test    r14, r14
0x180024df9  jnz     loc_180024F20
0x180024dff  test    r12, r12
0x180024e02  jz      short loc_180024E7F
0x180024e04  test    byte ptr [rsi+13h], 40h
0x180024e08  jnz     loc_180024F68
0x180024e0e  mov     edx, [rbx]; unsigned int
0x180024e10  test    edx, edx
0x180024e12  jz      loc_180024F61
0x180024e18  lea     eax, [rdx+7FFFFFFFh]
0x180024e1e  cmp     eax, 1
0x180024e21  jbe     loc_180024F5A
0x180024e27  lea     r9, [rbp+47h+var_C0]; int *
0x180024e2b  mov     rcx, rsi; this
0x180024e2e  lea     r8, [rbp+47h+var_B8]; unsigned int *
0x180024e32  call    ?_LoadProperty@CPropertySetStream@@AEAAPEAUtagSERIALIZEDPROPERTYVALUE@@KPEAKPEAJ@Z; CPropertySetStream::_LoadProperty(ulong,ulong *,long *)
0x180024e37  mov     edx, [rbp+47h+var_C0]
0x180024e3a  xor     ecx, ecx
0x180024e3c  test    edx, edx
0x180024e3e  cmovs   rax, rcx
0x180024e42  mov     [rbp+47h+pv], rax
0x180024e46  js      short loc_180024EA4
0x180024e48  cmp     [rbp+47h+var_BC], cl
0x180024e4b  jz      short loc_180024E67
0x180024e4d  lea     r8, [rbp+47h+var_C0]; int *
0x180024e51  mov     rdx, rdi; unsigned __int16 *
0x180024e54  mov     rcx, rsi; this
0x180024e57  call    ?DuplicatePropertyName@CPropertySetStream@@QEBAPEAGPEBGPEAJ@Z; CPropertySetStream::DuplicatePropertyName(ushort const *,long *)
0x180024e5c  mov     edx, [rbp+47h+var_C0]
0x180024e5f  mov     [r12], rax
0x180024e63  test    edx, edx
0x180024e65  js      short loc_180024EA4
0x180024e67  mov     eax, [rbx]
0x180024e69  mov     [r12+8], eax
0x180024e6e  mov     rax, [rbp+47h+pv]
0x180024e72  movzx   eax, word ptr [rax]
0x180024e75  mov     [r12+0Ch], ax
0x180024e7b  add     r12, 10h
0x180024e7f  mov     rcx, rdi; pv
0x180024e82  add     rbx, 4
0x180024e86  call    cs:__imp_CoTaskMemFree
0x180024e8c  mov     ecx, [rbp+47h+var_9C]
0x180024e8f  xor     edi, edi
0x180024e91  mov     [rbp+47h+pv], rdi
0x180024e95  jmp     loc_180024DA7
0x180024e9a  xor     al, al
0x180024e9c  mov     [rbp+47h+var_BC], al
0x180024e9f  jmp     loc_180024DF6
0x180024ea4  mov     rbx, [rbp+47h+var_B0]
0x180024ea8  mov     rcx, rsi; struct CPropertySetStream *
0x180024eab  call    ?Unlock@@YAJPEAVCPropertySetStream@@J@Z; Unlock(CPropertySetStream *,long)
0x180024eb0  mov     [rbp+47h+var_C0], eax
0x180024eb3  test    rdi, rdi
0x180024eb6  jz      loc_180024CFE
0x180024ebc  mov     rcx, rdi; pv
0x180024ebf  call    cs:__imp_CoTaskMemFree
0x180024ec5  jmp     loc_180024CFE
0x180024eca  mov     r8, r13
0x180024ecd  xor     edx, edx; Val
0x180024ecf  shl     r8, 4; Size
0x180024ed3  mov     rcx, r15; void *
0x180024ed6  call    memset_0
0x180024edb  jmp     loc_180024CE5
0x180024ee0  mov     [rbp+47h+var_B8], r13d
0x180024ee4  mov     eax, r13d
0x180024ee7  jmp     loc_180024D60
0x180024eec  cmp     eax, 14h
0x180024eef  jbe     short loc_180024F17
0x180024ef1  mov     ecx, eax
0x180024ef3  shl     rcx, 2; cb
0x180024ef7  call    cs:__imp_CoTaskMemAlloc
0x180024efd  mov     [rbp+47h+var_B0], rax
0x180024f01  mov     rbx, rax
0x180024f04  test    rax, rax
0x180024f07  jnz     loc_180024D6C
0x180024f0d  mov     edx, 0C000009Ah
0x180024f12  mov     [rbp+47h+var_C0], edx
0x180024f15  jmp     short loc_180024EA8
0x180024f17  lea     rbx, [rbp+47h+var_90]
0x180024f1b  jmp     loc_180024D6C
0x180024f20  test    al, al
0x180024f22  jz      short loc_180024F4B
0x180024f24  lea     r8, [rbp+47h+var_C0]; int *
0x180024f28  mov     rdx, rdi; unsigned __int16 *
0x180024f2b  mov     rcx, rsi; this
0x180024f2e  call    ?DuplicatePropertyName@CPropertySetStream@@QEBAPEAGPEBGPEAJ@Z; CPropertySetStream::DuplicatePropertyName(ushort const *,long *)
0x180024f33  mov     edx, [rbp+47h+var_C0]
0x180024f36  mov     [r14+8], rax
0x180024f3a  test    edx, edx
0x180024f3c  js      loc_180024EA4
0x180024f42  mov     dword ptr [r14], 0
0x180024f49  jmp     short loc_180024F51
0x180024f4b  mov     eax, [rbx]
0x180024f4d  mov     [r14+8], eax
0x180024f51  add     r14, 10h
0x180024f55  jmp     loc_180024DFF
0x180024f5a  mov     edx, 0C00000BBh
0x180024f5f  jmp     short loc_180024F71
0x180024f61  mov     edx, 0C000000Dh
0x180024f66  jmp     short loc_180024F71
0x180024f68  mov     edx, 0C0000022h
0x180024f6d  jmp     short loc_180024F71
0x180024f6f  xor     edx, edx
0x180024f71  mov     [rbp+47h+var_C0], edx
0x180024f74  jmp     loc_180024EA4
0x180024f79  test    r15, r15
0x180024f7c  jz      loc_180024D12
0x180024f82  mov     rsi, [rsi+20h]
0x180024f86  xor     ebx, ebx
0x180024f88  test    r13d, r13d
0x180024f8b  jz      loc_180024D12
0x180024f91  mov     edi, ebx
0x180024f93  add     rdi, rdi
0x180024f96  mov     rdx, [r15+rdi*8]
0x180024f9a  test    rdx, rdx
0x180024f9d  jz      short loc_180024FB6
0x180024f9f  mov     rax, [rsi]
0x180024fa2  mov     rcx, rsi
0x180024fa5  mov     rax, [rax+8]
0x180024fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fae  mov     qword ptr [r15+rdi*8], 0
0x180024fb6  inc     ebx
0x180024fb8  cmp     ebx, r13d
0x180024fbb  jb      short loc_180024F91
0x180024fbd  mov     eax, [rbp+47h+var_C0]
0x180024fc0  jmp     loc_180024D12
```
