# SyncContext_FindContextItemInContext(ushort const *,IOfflineFilesSyncContext *,IOfflineFilesSyncContextItem * *)

- ea: `0x18003dc0c`
- end: `0x18003dd38`
- name: `?SyncContext_FindContextItemInContext@@YAJPEBGPEAUIOfflineFilesSyncContext@@PEAPEAUIOfflineFilesSyncContextItem@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, struct IOfflineFilesSyncContext *, struct IOfflineFilesSyncContextItem **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ae68`

## callees

- `0x18003dc0c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dcee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dcee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003dccc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003dccc`

## pseudocode

```c
__int64 __fastcall SyncContext_FindContextItemInContext(
        PCNZWCH lpString1,
        struct IOfflineFilesSyncContext *a2,
        struct IOfflineFilesSyncContextItem **a3)
{
  __int64 v3; // rax
  int v6; // ebx
  struct IOfflineFilesSyncContextItem *v7; // rcx
  __int64 v9; // [rsp+30h] [rbp-10h] BYREF
  int v10; // [rsp+68h] [rbp+28h] BYREF
  struct IOfflineFilesSyncContextItem *v11; // [rsp+70h] [rbp+30h] BYREF
  PCNZWCH lpString2; // [rsp+78h] [rbp+38h] BYREF

  v3 = *(_QWORD *)a2;
  *a3 = 0;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContext *, __int64 *))(v3 + 64))(a2, &v9);
  if ( v6 >= 0 )
  {
    v11 = 0;
    v10 = 0;
    while ( !*a3 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, struct IOfflineFilesSyncContextItem **, int *))(*(_QWORD *)v9 + 24LL))(
             v9,
             1,
             &v11,
             &v10);
      if ( v6 )
        break;
      lpString2 = 0;
      v6 = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContextItem *, PCNZWCH *))(*(_QWORD *)v11 + 24LL))(
             v11,
             &lpString2);
      if ( v6 >= 0 )
      {
        if ( CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1) == 2 )
        {
          v7 = v11;
          *a3 = v11;
          (*(void (__fastcall **)(struct IOfflineFilesSyncContextItem *))(*(_QWORD *)v7 + 8LL))(v7);
        }
        CoTaskMemFree((LPVOID)lpString2);
      }
      (*(void (__fastcall **)(struct IOfflineFilesSyncContextItem *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    if ( v6 == 1 )
      v6 = -2147024894;
    (*(void (**)(void))(*(_QWORD *)v9 + 16LL))();
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003dc0c  mov     [rsp-18h+arg_0], rbx
0x18003dc11  push    rbp
0x18003dc12  push    rsi
0x18003dc13  push    rdi
0x18003dc14  mov     rbp, rsp
0x18003dc17  sub     rsp, 40h
0x18003dc1b  mov     rax, [rdx]
0x18003dc1e  mov     r9, rdx
0x18003dc21  mov     rsi, rcx
0x18003dc24  mov     qword ptr [r8], 0
0x18003dc2b  lea     rdx, [rbp+var_10]
0x18003dc2f  mov     [rbp+var_10], 0
0x18003dc37  mov     rcx, r9
0x18003dc3a  mov     rdi, r8
0x18003dc3d  mov     rax, [rax+40h]
0x18003dc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc46  mov     ebx, eax
0x18003dc48  test    eax, eax
0x18003dc4a  js      loc_18003DD29
0x18003dc50  mov     [rbp+arg_10], 0
0x18003dc58  mov     [rbp+arg_8], 0
0x18003dc5f  jmp     loc_18003DD04
0x18003dc64  mov     rcx, [rbp+var_10]
0x18003dc68  lea     r9, [rbp+arg_8]
0x18003dc6c  lea     r8, [rbp+arg_10]
0x18003dc70  mov     edx, 1
0x18003dc75  mov     rax, [rcx]
0x18003dc78  mov     rax, [rax+18h]
0x18003dc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc81  mov     ebx, eax
0x18003dc83  test    eax, eax
0x18003dc85  jnz     loc_18003DD0E
0x18003dc8b  mov     rcx, [rbp+arg_10]
0x18003dc8f  lea     rdx, [rbp+arg_18]
0x18003dc93  mov     [rbp+arg_18], 0
0x18003dc9b  mov     rax, [rcx]
0x18003dc9e  mov     rax, [rax+18h]
0x18003dca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dca7  mov     ebx, eax
0x18003dca9  test    eax, eax
0x18003dcab  js      short loc_18003DCF4
0x18003dcad  mov     rax, [rbp+arg_18]
0x18003dcb1  or      r9d, 0FFFFFFFFh; cchCount1
0x18003dcb5  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x18003dcbd  mov     r8, rsi; lpString1
0x18003dcc0  mov     [rsp+40h+lpString2], rax; lpString2
0x18003dcc5  lea     edx, [r9+2]; dwCmpFlags
0x18003dcc9  lea     ecx, [rdx+7Eh]; Locale
0x18003dccc  call    cs:__imp_CompareStringW
0x18003dcd2  cmp     eax, 2
0x18003dcd5  jnz     short loc_18003DCEA
0x18003dcd7  mov     rcx, [rbp+arg_10]
0x18003dcdb  mov     [rdi], rcx
0x18003dcde  mov     rax, [rcx]
0x18003dce1  mov     rax, [rax+8]
0x18003dce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcea  mov     rcx, [rbp+arg_18]; pv
0x18003dcee  call    cs:__imp_CoTaskMemFree
0x18003dcf4  mov     rcx, [rbp+arg_10]
0x18003dcf8  mov     rax, [rcx]
0x18003dcfb  mov     rax, [rax+10h]
0x18003dcff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd04  cmp     qword ptr [rdi], 0
0x18003dd08  jz      loc_18003DC64
0x18003dd0e  mov     rcx, [rbp+var_10]
0x18003dd12  cmp     ebx, 1
0x18003dd15  mov     eax, 80070002h
0x18003dd1a  cmovz   ebx, eax
0x18003dd1d  mov     rax, [rcx]
0x18003dd20  mov     rax, [rax+10h]
0x18003dd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd29  mov     eax, ebx
0x18003dd2b  mov     rbx, [rsp+40h+arg_0]
0x18003dd30  add     rsp, 40h
0x18003dd34  pop     rdi
0x18003dd35  pop     rsi
0x18003dd36  pop     rbp
0x18003dd37  retn
```
