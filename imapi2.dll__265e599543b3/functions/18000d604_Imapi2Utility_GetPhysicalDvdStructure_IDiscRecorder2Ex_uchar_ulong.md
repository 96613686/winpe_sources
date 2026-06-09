# Imapi2Utility::GetPhysicalDvdStructure(IDiscRecorder2Ex *,uchar * *,ulong *)

- ea: `0x18000d604`
- end: `0x18000d7ba`
- name: `?GetPhysicalDvdStructure@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAPEAEPEAK@Z`
- size: `438`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180009b80`

## callees

- `0x18000d604`
- `0x1800140f4`
- `0x180016778`
- `0x1800236b4`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000d6b6`
- `ole32!CoTaskMemFree` at `0x18000d6b6`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::GetPhysicalDvdStructure(
        Imapi2Utility *this,
        struct IDiscRecorder2Ex *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  PVOID *v7; // rcx
  int v8; // ebx
  unsigned int v10; // eax
  PVOID *v11; // rcx
  unsigned int v12; // r8d
  unsigned int v13; // [rsp+68h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  pv = 0;
  v13 = 0;
  if ( a2 )
  {
    v8 = 0;
    a2->lpVtbl = 0;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = -2147467261;
  }
  if ( a3 )
  {
    *(_DWORD *)a3 = 0;
    if ( v8 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(Imapi2Utility *, _QWORD, _QWORD, _QWORD, _DWORD, LPVOID *, unsigned int *))(*(_QWORD *)this + 48LL))(
              this,
              0,
              0,
              0,
              0,
              &pv,
              &v13);
      v8 = v10;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v10);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 >= 0 )
      {
        v12 = v13;
        if ( v13 >= 0x11 )
        {
          a2->lpVtbl = (struct IDiscRecorder2ExVtbl *)pv;
          *(_DWORD *)a3 = v12;
          return (unsigned int)v8;
        }
        v8 = -1062599937;
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 3u )
          WPP_SF_DDDd(v11[2], 13, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      }
    }
  }
  else
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 3u )
      WPP_SF_(v7[2], 11, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
    v8 = -2147467261;
  }
  CoTaskMemFree(pv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d604  mov     [rsp+arg_0], rbx
0x18000d609  push    rsi
0x18000d60a  push    rdi
0x18000d60b  push    r14
0x18000d60d  sub     rsp, 40h
0x18000d611  mov     [rsp+58h+pv], 0
0x18000d61a  mov     rdi, r8
0x18000d61d  mov     [rsp+58h+arg_8], 0
0x18000d625  mov     rsi, rdx
0x18000d628  lea     rax, WPP_GLOBAL_Control
0x18000d62f  mov     r14, rcx
0x18000d632  test    rdx, rdx
0x18000d635  jnz     short loc_18000D677
0x18000d637  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d63e  cmp     rcx, rax
0x18000d641  jz      short loc_18000D670
0x18000d643  test    byte ptr [rcx+1Ch], 4
0x18000d647  jz      short loc_18000D670
0x18000d649  cmp     byte ptr [rcx+19h], 3
0x18000d64d  jb      short loc_18000D670
0x18000d64f  mov     rcx, [rcx+10h]
0x18000d653  lea     edx, [rsi+0Ah]
0x18000d656  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18000d65d  call    WPP_SF_
0x18000d662  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d669  lea     rax, WPP_GLOBAL_Control
0x18000d670  mov     ebx, 80004003h
0x18000d675  jmp     short loc_18000D683
0x18000d677  xor     ebx, ebx
0x18000d679  mov     [rdx], rbx
0x18000d67c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d683  test    rdi, rdi
0x18000d686  jnz     short loc_18000D6CC
0x18000d688  cmp     rcx, rax
0x18000d68b  jz      short loc_18000D6AC
0x18000d68d  test    byte ptr [rcx+1Ch], 4
0x18000d691  jz      short loc_18000D6AC
0x18000d693  cmp     byte ptr [rcx+19h], 3
0x18000d697  jb      short loc_18000D6AC
0x18000d699  mov     rcx, [rcx+10h]
0x18000d69d  lea     edx, [rdi+0Bh]
0x18000d6a0  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18000d6a7  call    WPP_SF_
0x18000d6ac  mov     ebx, 80004003h
0x18000d6b1  mov     rcx, [rsp+58h+pv]; pv
0x18000d6b6  call    cs:__imp_CoTaskMemFree
0x18000d6bc  mov     eax, ebx
0x18000d6be  mov     rbx, [rsp+58h+arg_0]
0x18000d6c3  add     rsp, 40h
0x18000d6c7  pop     r14
0x18000d6c9  pop     rdi
0x18000d6ca  pop     rsi
0x18000d6cb  retn
0x18000d6cc  mov     dword ptr [rdi], 0
0x18000d6d2  test    ebx, ebx
0x18000d6d4  js      short loc_18000D6B1
0x18000d6d6  mov     rax, [r14]
0x18000d6d9  lea     rcx, [rsp+58h+arg_8]
0x18000d6de  mov     [rsp+58h+var_28], rcx
0x18000d6e3  xor     r9d, r9d
0x18000d6e6  lea     rcx, [rsp+58h+pv]
0x18000d6eb  xor     r8d, r8d
0x18000d6ee  mov     [rsp+58h+var_30], rcx
0x18000d6f3  xor     edx, edx
0x18000d6f5  mov     rax, [rax+30h]
0x18000d6f9  mov     rcx, r14
0x18000d6fc  mov     [rsp+58h+var_38], 0
0x18000d704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d709  mov     ebx, eax
0x18000d70b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d712  lea     r14, WPP_GLOBAL_Control
0x18000d719  cmp     rcx, r14
0x18000d71c  jz      short loc_18000D749
0x18000d71e  test    byte ptr [rcx+1Ch], 4
0x18000d722  jz      short loc_18000D749
0x18000d724  cmp     byte ptr [rcx+19h], 3
0x18000d728  jb      short loc_18000D749
0x18000d72a  mov     rcx, [rcx+10h]
0x18000d72e  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18000d735  mov     edx, 0Ch
0x18000d73a  mov     r9d, eax
0x18000d73d  call    WPP_SF_d
0x18000d742  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d749  test    ebx, ebx
0x18000d74b  js      loc_18000D6B1
0x18000d751  mov     r8d, [rsp+58h+arg_8]
0x18000d756  mov     eax, 11h
0x18000d75b  cmp     r8d, eax
0x18000d75e  jnb     short loc_18000D7AA
0x18000d760  mov     ebx, 0C0AA02FFh
0x18000d765  cmp     rcx, r14
0x18000d768  jz      loc_18000D6B1
0x18000d76e  test    byte ptr [rcx+1Ch], 4
0x18000d772  jz      loc_18000D6B1
0x18000d778  cmp     byte ptr [rcx+19h], 3
0x18000d77c  jb      loc_18000D6B1
0x18000d782  mov     rcx, [rcx+10h]
0x18000d786  lea     edx, [rax-4]
0x18000d789  mov     dword ptr [rsp+58h+var_28], eax
0x18000d78d  mov     r9d, r8d
0x18000d790  mov     dword ptr [rsp+58h+var_30], eax
0x18000d794  mov     [rsp+58h+var_38], r8d
0x18000d799  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18000d7a0  call    WPP_SF_DDDd
0x18000d7a5  jmp     loc_18000D6B1
0x18000d7aa  mov     rax, [rsp+58h+pv]
0x18000d7af  mov     [rsi], rax
0x18000d7b2  mov     [rdi], r8d
0x18000d7b5  jmp     loc_18000D6BC
```
