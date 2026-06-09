# CNetDiagHelperImpl::UserActionRepair(ulong *,ulong,long *,tagREPAIR_STATUS *)

- ea: `0x1800182c4`
- end: `0x180018372`
- name: `?UserActionRepair@CNetDiagHelperImpl@@IEAAJPEAKKPEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, unsigned int *, int, int *, enum tagREPAIR_STATUS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000ebe0`

## callees

- `0x1800182c4`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018329`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018329`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetDiagHelperImpl::UserActionRepair(
        CNetDiagHelperImpl *this,
        unsigned int *a2,
        int a3,
        int *a4,
        enum tagREPAIR_STATUS *a5)
{
  enum tagREPAIR_STATUS *v5; // rbx
  __int64 v8; // rax
  int v9; // esi
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = a3;
  v5 = a5;
  pv = 0;
  LODWORD(a5) = 0;
  *v5 = RS_UNREPAIRED;
  v8 = *(_QWORD *)this;
  v12 = 0;
  v9 = (*(__int64 (__fastcall **)(CNetDiagHelperImpl *, _QWORD, LPVOID *, enum tagREPAIR_STATUS **, int *))(v8 + 48))(
         this,
         0,
         &pv,
         &a5,
         &v12);
  if ( v9 >= 0 )
  {
    CoTaskMemFree(pv);
    if ( v12 == 2 )
    {
      *v5 = RS_REPAIRED;
    }
    else if ( !*a2 && (v12 == 1 || v12 == 4) )
    {
      *a2 = 1;
      *a4 = 1;
      *v5 = RS_DEFERRED;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800182c4  mov     r11, rsp
0x1800182c7  mov     [r11+10h], rbx
0x1800182cb  mov     [r11+18h], r8d
0x1800182cf  push    rsi
0x1800182d0  push    rdi
0x1800182d1  push    r14
0x1800182d3  sub     rsp, 30h
0x1800182d7  mov     rbx, [rsp+48h+arg_20]
0x1800182dc  lea     r8, [r11+8]
0x1800182e0  mov     rdi, rdx
0x1800182e3  mov     qword ptr [r11+8], 0
0x1800182eb  lea     rdx, [r11+18h]
0x1800182ef  mov     dword ptr [rsp+48h+arg_20], 0
0x1800182f7  mov     r14, r9
0x1800182fa  mov     [r11-28h], rdx
0x1800182fe  mov     dword ptr [rbx], 2
0x180018304  lea     r9, [r11+28h]
0x180018308  mov     rax, [rcx]
0x18001830b  xor     edx, edx
0x18001830d  mov     [rsp+48h+arg_10], 0
0x180018315  mov     rax, [rax+30h]
0x180018319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001831e  mov     esi, eax
0x180018320  test    eax, eax
0x180018322  js      short loc_180018362
0x180018324  mov     rcx, [rsp+48h+pv]; pv
0x180018329  call    cs:__imp_CoTaskMemFree
0x18001832f  mov     ecx, [rsp+48h+arg_10]
0x180018333  cmp     ecx, 2
0x180018336  jnz     short loc_180018340
0x180018338  mov     dword ptr [rbx], 1
0x18001833e  jmp     short loc_180018362
0x180018340  mov     eax, [rdi]
0x180018342  cmp     eax, 1
0x180018345  jnb     short loc_180018362
0x180018347  cmp     ecx, 1
0x18001834a  jz      short loc_180018351
0x18001834c  cmp     ecx, 4
0x18001834f  jnz     short loc_180018362
0x180018351  inc     eax
0x180018353  mov     [rdi], eax
0x180018355  mov     dword ptr [r14], 1
0x18001835c  mov     dword ptr [rbx], 3
0x180018362  mov     rbx, [rsp+48h+arg_8]
0x180018367  mov     eax, esi
0x180018369  add     rsp, 30h
0x18001836d  pop     r14
0x18001836f  pop     rdi
0x180018370  pop     rsi
0x180018371  retn
```
