# AcquireTemporaryResourcesForAllocation

- ea: `0x1400c5bc8`
- end: `0x1400c5e95`
- name: `AcquireTemporaryResourcesForAllocation`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1400c8d24`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140030ae0`
- `0x1400335c4`
- `0x1400336b8`
- `0x140058680`
- `0x140058760`
- `0x140058ac0`
- `0x1400c5bc8`
- `0x1400e80f0`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x1400c5cd3`
- `watchdog!WdLogSingleEntry2` at `0x1400c5e2b`
- `watchdog!WdLogSingleEntry2` at `0x1400c5cd3`
- `watchdog!WdLogSingleEntry2` at `0x1400c5e2b`
- `watchdog!WdLogSingleEntry1` at `0x1400c5d8e`
- `watchdog!WdLogSingleEntry1` at `0x1400c5d8e`
- `dxgkrnl!SysMmMapPagesToIommu` at `0x1400c5d76`
- `dxgkrnl!SysMmMapPagesToIommu` at `0x1400c5d76`

## string_xrefs

- `0x1400c5e40`: `Failed to allocate VIDMM_TEMPORARY_RESOURCE for memory transfer`

## pseudocode

```c
_QWORD *__fastcall AcquireTemporaryResourcesForAllocation(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // r15
  __int64 v6; // r13
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  __int64 v12; // r12
  __int64 v13; // r14
  int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // r12
  bool v17; // bl
  unsigned __int64 LogicalAddress; // rax
  int v19; // eax
  _QWORD *v20; // rdx
  _QWORD *result; // rax
  int v22; // ecx
  int v23; // r8d
  int v24; // [rsp+20h] [rbp-D8h]
  __int64 v27; // [rsp+58h] [rbp-A0h]
  _BYTE v28[64]; // [rsp+60h] [rbp-98h] BYREF

  v4 = *(_QWORD *)(a1 + 56);
  v6 = *(_QWORD *)a2;
  v10 = (_QWORD *)operator new(72, 1714776406, 256);
  v11 = v10;
  if ( !v10 )
  {
    _InterlockedIncrement(&dword_1400868C0);
    WdLogSingleEntry2(6, a1, a2);
    WdLogGlobalForLineNumber = 63;
    DxgkLogInternalTriageEvent(
      v22,
      262145,
      v23,
      (unsigned int)L"Failed to allocate VIDMM_TEMPORARY_RESOURCE for memory transfer",
      a1,
      a2,
      0,
      0);
    return 0;
  }
  memset(v10, 0, 0x48u);
  v11[3] = (unsigned __int64)a3 << 12;
  v11[4] = (unsigned __int64)a4 << 12;
  v12 = *(_QWORD *)(v6 + 240);
  v13 = *(_QWORD *)(v6 + 232);
  v27 = v12;
  VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
    (VIDMM_PROCESS_AUTOATTACH *)v28,
    *(struct VIDMM_PROCESS **)(*(_QWORD *)(v6 + 48) + 8LL),
    1);
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _QWORD, int, __int64, char))(*(_QWORD *)v13 + 16LL))(
          v13,
          v12,
          v6,
          v11[3],
          v11[4],
          ~(unsigned __int8)(*(_DWORD *)(v6 + 24) >> 5) & 2,
          v4,
          1);
  VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v28);
  if ( v14 < 0 )
  {
    WdLogSingleEntry2(3, a3, a4);
    WdLogGlobalForLineNumber = 90;
LABEL_8:
    if ( (v11[5] & 2) != 0 )
    {
      LOBYTE(v24) = 1;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v13 + 24LL))(
        v13,
        v12,
        v11[3],
        v11[4],
        v24);
      *((_DWORD *)v11 + 10) &= ~2u;
    }
    operator delete(v11);
    return 0;
  }
  *((_DWORD *)v11 + 10) |= 2u;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v13 + 72LL))(v13, v12, v11[3], v11[4]);
  v11[2] = v15;
  v16 = v15;
  if ( *(_BYTE *)(v4 + 36258) )
  {
    if ( (v11[5] & 1) == 0 )
    {
      v17 = (**(_DWORD **)(v6 + 384) & 0x10) != 0;
      LogicalAddress = VidMmiGetLogicalAddress(*(void **)(*(_QWORD *)a2 + 360LL), v11[3]);
      LOBYTE(v24) = v17;
      v19 = SysMmMapPagesToIommu(*(_QWORD *)(*(_QWORD *)(v4 + 24) + 224LL), LogicalAddress, v16, a4, v24, 3, a2);
      if ( v19 < 0 )
      {
        WdLogSingleEntry1(3, v19);
        v12 = v27;
        WdLogGlobalForLineNumber = 121;
        goto LABEL_8;
      }
    }
  }
  v11[8] = a2;
  v20 = *(_QWORD **)(a2 + 112);
  if ( *v20 != a2 + 104 )
    __fastfail(3u);
  v11[6] = a2 + 104;
  v11[7] = v20;
  *v20 = v11 + 6;
  *(_QWORD *)(a2 + 112) = v11 + 6;
  result = v11;
  *(_DWORD *)(a2 + 64) |= 0x40u;
  ++*(_DWORD *)(a1 + 2352);
  return result;
}

```

## disassembly

```asm
0x1400c5bc8  push    rbx
0x1400c5bca  push    rbp
0x1400c5bcb  push    rsi
0x1400c5bcc  push    rdi
0x1400c5bcd  push    r12
0x1400c5bcf  push    r13
0x1400c5bd1  push    r14
0x1400c5bd3  push    r15
0x1400c5bd5  sub     rsp, 0B8h
0x1400c5bdc  mov     rax, cs:__security_cookie
0x1400c5be3  xor     rax, rsp
0x1400c5be6  mov     [rsp+0F8h+var_58], rax
0x1400c5bee  mov     r15, [rcx+38h]
0x1400c5bf2  mov     rsi, rdx
0x1400c5bf5  mov     r13, [rdx]
0x1400c5bf8  mov     rbp, rcx
0x1400c5bfb  mov     ebx, r8d
0x1400c5bfe  mov     r12d, 48h ; 'H'
0x1400c5c04  mov     r14d, r9d
0x1400c5c07  mov     ecx, r12d
0x1400c5c0a  mov     edx, 66356956h
0x1400c5c0f  mov     [rsp+0F8h+var_A8], r14d
0x1400c5c14  mov     r8d, 100h
0x1400c5c1a  mov     [rsp+0F8h+var_A4], ebx
0x1400c5c1e  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400c5c23  mov     rdi, rax
0x1400c5c26  test    rax, rax
0x1400c5c29  jz      loc_1400C5E19
0x1400c5c2f  mov     r8d, r12d; Size
0x1400c5c32  xor     edx, edx; Val
0x1400c5c34  mov     rcx, rax; void *
0x1400c5c37  call    memset
0x1400c5c3c  mov     eax, ebx
0x1400c5c3e  lea     rcx, [rsp+0F8h+var_98]; this
0x1400c5c43  shl     rax, 0Ch
0x1400c5c47  mov     r8b, 1; bool
0x1400c5c4a  mov     [rdi+18h], rax
0x1400c5c4e  mov     eax, r14d
0x1400c5c51  shl     rax, 0Ch
0x1400c5c55  mov     [rdi+20h], rax
0x1400c5c59  mov     rdx, [r13+30h]
0x1400c5c5d  mov     r12, [r13+0F0h]
0x1400c5c64  mov     r14, [r13+0E8h]
0x1400c5c6b  mov     [rsp+0F8h+var_A0], r12
0x1400c5c70  mov     rdx, [rdx+8]; struct VIDMM_PROCESS *
0x1400c5c74  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400c5c79  mov     ecx, [r13+18h]
0x1400c5c7d  mov     r8, r13
0x1400c5c80  mov     rax, [r14]
0x1400c5c83  mov     rdx, r12
0x1400c5c86  mov     r9, [rdi+18h]
0x1400c5c8a  shr     ecx, 5
0x1400c5c8d  not     ecx
0x1400c5c8f  mov     byte ptr [rsp+0F8h+var_C0], 1
0x1400c5c94  mov     rax, [rax+10h]
0x1400c5c98  and     ecx, 2
0x1400c5c9b  mov     [rsp+0F8h+var_C8], r15
0x1400c5ca0  mov     dword ptr [rsp+0F8h+var_D0], ecx
0x1400c5ca4  mov     rcx, [rdi+20h]
0x1400c5ca8  mov     [rsp+0F8h+var_D8], rcx
0x1400c5cad  mov     rcx, r14
0x1400c5cb0  call    _guard_dispatch_icall
0x1400c5cb5  lea     rcx, [rsp+0F8h+var_98]; this
0x1400c5cba  mov     ebx, eax
0x1400c5cbc  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400c5cc1  test    ebx, ebx
0x1400c5cc3  jns     short loc_1400C5CEE
0x1400c5cc5  mov     r8d, [rsp+0F8h+var_A8]
0x1400c5cca  mov     ecx, 3
0x1400c5ccf  mov     edx, [rsp+0F8h+var_A4]
0x1400c5cd3  call    cs:__imp_WdLogSingleEntry2
0x1400c5cda  nop     dword ptr [rax+rax+00h]
0x1400c5cdf  mov     cs:WdLogGlobalForLineNumber, 5Ah ; 'Z'
0x1400c5ce9  jmp     loc_1400C5DA9
0x1400c5cee  or      dword ptr [rdi+28h], 2
0x1400c5cf2  mov     rdx, r12
0x1400c5cf5  mov     rax, [r14]
0x1400c5cf8  mov     rcx, r14
0x1400c5cfb  mov     r9, [rdi+20h]
0x1400c5cff  mov     r8, [rdi+18h]
0x1400c5d03  mov     rax, [rax+48h]
0x1400c5d07  call    _guard_dispatch_icall
0x1400c5d0c  mov     [rdi+10h], rax
0x1400c5d10  mov     r12, rax
0x1400c5d13  cmp     byte ptr [r15+8DA2h], 0
0x1400c5d1b  jz      loc_1400C5DE0
0x1400c5d21  mov     ecx, [rdi+28h]
0x1400c5d24  test    cl, 1
0x1400c5d27  jnz     loc_1400C5DE0
0x1400c5d2d  mov     rcx, [r13+180h]
0x1400c5d34  mov     rdx, [rdi+18h]; unsigned __int64
0x1400c5d38  mov     ebx, [rcx]
0x1400c5d3a  mov     rcx, [rsi]
0x1400c5d3d  shr     ebx, 4
0x1400c5d40  and     bl, 1
0x1400c5d43  mov     rcx, [rcx+168h]; void *
0x1400c5d4a  call    ?VidMmiGetLogicalAddress@@YA_KPEAX_K@Z; VidMmiGetLogicalAddress(void *,unsigned __int64)
0x1400c5d4f  mov     rcx, [r15+18h]
0x1400c5d53  mov     r8, r12
0x1400c5d56  mov     r9d, [rsp+0F8h+var_A8]
0x1400c5d5b  mov     rdx, rax
0x1400c5d5e  mov     [rsp+0F8h+var_C8], rsi
0x1400c5d63  mov     dword ptr [rsp+0F8h+var_D0], 3
0x1400c5d6b  mov     rcx, [rcx+0E0h]
0x1400c5d72  mov     byte ptr [rsp+0F8h+var_D8], bl
0x1400c5d76  call    cs:__imp_?SysMmMapPagesToIommu@@YAJPEAUSYSMM_ADAPTER@@_KPEB_K1_NW4SYSMM_MAPPING_OBJECT_TYPE@@PEBX@Z; SysMmMapPagesToIommu(SYSMM_ADAPTER *,unsigned __int64,unsigned __int64 const *,unsigned __int64,bool,SYSMM_MAPPING_OBJECT_TYPE,void const *)
0x1400c5d7d  nop     dword ptr [rax+rax+00h]
0x1400c5d82  test    eax, eax
0x1400c5d84  jns     short loc_1400C5DE0
0x1400c5d86  movsxd  rdx, eax
0x1400c5d89  mov     ecx, 3
0x1400c5d8e  call    cs:__imp_WdLogSingleEntry1
0x1400c5d95  nop     dword ptr [rax+rax+00h]
0x1400c5d9a  mov     r12, [rsp+0F8h+var_A0]
0x1400c5d9f  mov     cs:WdLogGlobalForLineNumber, 79h ; 'y'
0x1400c5da9  mov     eax, [rdi+28h]
0x1400c5dac  test    al, 2
0x1400c5dae  jz      short loc_1400C5DD3
0x1400c5db0  mov     rax, [r14]
0x1400c5db3  mov     rdx, r12
0x1400c5db6  mov     r9, [rdi+20h]
0x1400c5dba  mov     rcx, r14
0x1400c5dbd  mov     r8, [rdi+18h]
0x1400c5dc1  mov     byte ptr [rsp+0F8h+var_D8], 1
0x1400c5dc6  mov     rax, [rax+18h]
0x1400c5dca  call    _guard_dispatch_icall
0x1400c5dcf  and     dword ptr [rdi+28h], 0FFFFFFFDh
0x1400c5dd3  mov     rcx, rdi; void *
0x1400c5dd6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c5ddb  jmp     loc_1400C5E6E
0x1400c5de0  lea     rcx, [rsi+68h]
0x1400c5de4  mov     [rdi+40h], rsi
0x1400c5de8  mov     rdx, [rcx+8]
0x1400c5dec  cmp     [rdx], rcx
0x1400c5def  jz      short loc_1400C5DF8
0x1400c5df1  mov     ecx, 3
0x1400c5df6  int     29h; Win8: RtlFailFast(ecx)
0x1400c5df8  lea     rax, [rdi+30h]
0x1400c5dfc  mov     [rax], rcx
0x1400c5dff  mov     [rax+8], rdx
0x1400c5e03  mov     [rdx], rax
0x1400c5e06  mov     [rcx+8], rax
0x1400c5e0a  mov     rax, rdi
0x1400c5e0d  or      dword ptr [rsi+40h], 40h
0x1400c5e11  inc     dword ptr [rbp+930h]
0x1400c5e17  jmp     short loc_1400C5E70
0x1400c5e19  lock inc cs:dword_1400868C0
0x1400c5e20  mov     r8, rsi
0x1400c5e23  mov     rdx, rbp
0x1400c5e26  mov     ecx, 6
0x1400c5e2b  call    cs:__imp_WdLogSingleEntry2
0x1400c5e32  nop     dword ptr [rax+rax+00h]
0x1400c5e37  mov     [rsp+0F8h+var_C0], 0
0x1400c5e40  lea     r9, aFailedToAlloca_79; "Failed to allocate VIDMM_TEMPORARY_RESO"...
0x1400c5e47  mov     [rsp+0F8h+var_C8], 0
0x1400c5e50  mov     edx, 40001h
0x1400c5e55  mov     [rsp+0F8h+var_D0], rsi
0x1400c5e5a  mov     [rsp+0F8h+var_D8], rbp
0x1400c5e5f  mov     cs:WdLogGlobalForLineNumber, 3Fh ; '?'
0x1400c5e69  call    DxgkLogInternalTriageEvent
0x1400c5e6e  xor     eax, eax
0x1400c5e70  mov     rcx, [rsp+0F8h+var_58]
0x1400c5e78  xor     rcx, rsp; StackCookie
0x1400c5e7b  call    __security_check_cookie
0x1400c5e80  add     rsp, 0B8h
0x1400c5e87  pop     r15
0x1400c5e89  pop     r14
0x1400c5e8b  pop     r13
0x1400c5e8d  pop     r12
0x1400c5e8f  pop     rdi
0x1400c5e90  pop     rsi
0x1400c5e91  pop     rbp
0x1400c5e92  pop     rbx
0x1400c5e93  retn
```
