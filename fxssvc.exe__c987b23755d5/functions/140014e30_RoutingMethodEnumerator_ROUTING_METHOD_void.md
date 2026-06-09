# RoutingMethodEnumerator(_ROUTING_METHOD *,void *)

- ea: `0x140014e30`
- end: `0x14001514c`
- name: `?RoutingMethodEnumerator@@YAHPEAU_ROUTING_METHOD@@PEAX@Z`
- size: `796`
- prototype: `__int64 __fastcall(struct _ROUTING_METHOD *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x140014e30`
- `0x140024850`
- `0x1400670fc`
- `0x140085010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140014f79`
- `ole32!CoTaskMemFree` at `0x140014f79`
- `ole32!StringFromIID` at `0x140014e69`
- `ole32!StringFromIID` at `0x140014f9e`
- `ole32!StringFromIID` at `0x140014e69`
- `ole32!StringFromIID` at `0x140014f9e`

## pseudocode

```c
__int64 __fastcall RoutingMethodEnumerator(struct _ROUTING_METHOD *a1, _DWORD *a2)
{
  void *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rax
  int v7; // edx
  int v8; // r9d
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  int v12; // r9d
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  int v16; // r10d
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  int v20; // r9d
  __int64 v21; // rax
  int v22; // eax
  int v23; // r8d
  LPVOID pv; // [rsp+90h] [rbp+18h] BYREF
  char *v26; // [rsp+98h] [rbp+20h]

  pv = 0;
  if ( *a2 == 1 )
  {
    a2[1] += 64;
    StringFromIID((const IID *const)a1 + 2, (LPOLESTR *)&pv);
    v4 = pv;
    v5 = -1;
    if ( pv )
    {
      v6 = -1;
      do
        ++v6;
      while ( *((_WORD *)pv + v6) );
      v7 = 2 * v6 + 2;
    }
    else
    {
      v7 = 0;
    }
    v8 = v7 + a2[1];
    a2[1] = v8;
    v9 = *(_QWORD *)(*((_QWORD *)a2 + 2) + 56LL);
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(v9 + 2 * v10) );
      v11 = 2 * v10 + 2;
    }
    else
    {
      v11 = 0;
    }
    v12 = v11 + v8;
    a2[1] = v12;
    v13 = *((_QWORD *)a1 + 7);
    if ( v13 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(v13 + 2 * v14) );
      v15 = 2 * v14 + 2;
    }
    else
    {
      v15 = 0;
    }
    v16 = v15 + v12;
    a2[1] = v15 + v12;
    v17 = *((_QWORD *)a1 + 8);
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v17 + 2 * v18) );
      v19 = 2 * v18 + 2;
    }
    else
    {
      v19 = 0;
    }
    v20 = v19 + v16;
    a2[1] = v19 + v16;
    if ( *((_QWORD *)a1 + 11) == -572 )
    {
      v22 = 0;
    }
    else
    {
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(*((_QWORD *)a1 + 11) + 572LL + 2 * v21) );
      v22 = 2 * v21 + 2;
    }
    a2[1] = v22 + v20;
    if ( *((_QWORD *)a1 + 11) == -52 )
    {
      v23 = 0;
    }
    else
    {
      do
        ++v5;
      while ( *(_WORD *)(*((_QWORD *)a1 + 11) + 52LL + 2 * v5) );
      v23 = 2 * v5 + 2;
    }
    a2[1] = v23 + v22 + v20;
    goto LABEL_32;
  }
  if ( *a2 == 2 )
  {
    StringFromIID((const IID *const)a1 + 2, (LPOLESTR *)&pv);
    v26 = (char *)(a2 + 1);
    *(_DWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *((_QWORD *)a2 + 3)) = 64;
    *(_DWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *((_QWORD *)a2 + 3) + 4) = *(_DWORD *)(*((_QWORD *)a2 + 2) + 24LL);
    *(_DWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *((_QWORD *)a2 + 3) + 8) = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*((_QWORD *)a1 + 11) + 1656LL))(
                                                                                            pv,
                                                                                            *(unsigned int *)(*((_QWORD *)a2 + 2) + 24LL),
                                                                                            -1);
    StoreString(*(unsigned __int16 **)(*((_QWORD *)a2 + 2) + 56LL), a2[8]);
    StoreString((unsigned __int16 *)pv, a2[8]);
    StoreString(*((unsigned __int16 **)a1 + 8), a2[8]);
    StoreString(*((unsigned __int16 **)a1 + 7), a2[8]);
    StoreString((unsigned __int16 *)(*((_QWORD *)a1 + 11) + 572LL), a2[8]);
    StoreString((unsigned __int16 *)(*((_QWORD *)a1 + 11) + 52LL), a2[8]);
    ++a2[1];
    v4 = pv;
LABEL_32:
    CoTaskMemFree(v4);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140014e30  mov     rax, rsp
0x140014e33  mov     [rax+10h], rdx
0x140014e37  mov     [rax+8], rcx
0x140014e3b  push    rbx
0x140014e3c  push    rsi
0x140014e3d  push    rdi
0x140014e3e  push    r12
0x140014e40  push    r14
0x140014e42  push    r15
0x140014e44  sub     rsp, 48h
0x140014e48  mov     rdi, rdx
0x140014e4b  mov     rsi, rcx
0x140014e4e  xor     ebx, ebx
0x140014e50  mov     [rax+18h], rbx
0x140014e54  cmp     dword ptr [rdx], 1
0x140014e57  jnz     loc_140014F89
0x140014e5d  add     dword ptr [rdx+4], 40h ; '@'
0x140014e61  add     rcx, 20h ; ' '; rclsid
0x140014e65  lea     rdx, [rax+18h]; lplpsz
0x140014e69  call    cs:__imp_StringFromIID
0x140014e6f  mov     rcx, [rsp+78h+pv]; pv
0x140014e77  or      r8, 0FFFFFFFFFFFFFFFFh
0x140014e7b  test    rcx, rcx
0x140014e7e  jz      short loc_140014E96
0x140014e80  mov     rax, r8
0x140014e83  inc     rax
0x140014e86  cmp     [rcx+rax*2], bx
0x140014e8a  jnz     short loc_140014E83
0x140014e8c  lea     rdx, ds:2[rax*2]
0x140014e94  jmp     short loc_140014E99
0x140014e96  mov     rdx, rbx
0x140014e99  mov     r9d, [rdi+4]
0x140014e9d  add     r9d, edx
0x140014ea0  mov     [rdi+4], r9d
0x140014ea4  mov     rax, [rdi+10h]
0x140014ea8  mov     rdx, [rax+38h]
0x140014eac  test    rdx, rdx
0x140014eaf  jz      short loc_140014EC7
0x140014eb1  mov     rax, r8
0x140014eb4  inc     rax
0x140014eb7  cmp     [rdx+rax*2], bx
0x140014ebb  jnz     short loc_140014EB4
0x140014ebd  lea     rax, ds:2[rax*2]
0x140014ec5  jmp     short loc_140014ECA
0x140014ec7  mov     rax, rbx
0x140014eca  add     r9d, eax
0x140014ecd  mov     [rdi+4], r9d
0x140014ed1  mov     rdx, [rsi+38h]
0x140014ed5  test    rdx, rdx
0x140014ed8  jz      short loc_140014EF0
0x140014eda  mov     rax, r8
0x140014edd  inc     rax
0x140014ee0  cmp     [rdx+rax*2], bx
0x140014ee4  jnz     short loc_140014EDD
0x140014ee6  lea     rax, ds:2[rax*2]
0x140014eee  jmp     short loc_140014EF3
0x140014ef0  mov     rax, rbx
0x140014ef3  lea     r10d, [rax+r9]
0x140014ef7  mov     [rdi+4], r10d
0x140014efb  mov     rdx, [rsi+40h]
0x140014eff  test    rdx, rdx
0x140014f02  jz      short loc_140014F1A
0x140014f04  mov     rax, r8
0x140014f07  inc     rax
0x140014f0a  cmp     [rdx+rax*2], bx
0x140014f0e  jnz     short loc_140014F07
0x140014f10  lea     rax, ds:2[rax*2]
0x140014f18  jmp     short loc_140014F1D
0x140014f1a  mov     rax, rbx
0x140014f1d  lea     r9d, [rax+r10]
0x140014f21  mov     [rdi+4], r9d
0x140014f25  mov     rdx, [rsi+58h]
0x140014f29  add     rdx, 23Ch
0x140014f30  jz      short loc_140014F48
0x140014f32  mov     rax, r8
0x140014f35  inc     rax
0x140014f38  cmp     [rdx+rax*2], bx
0x140014f3c  jnz     short loc_140014F35
0x140014f3e  lea     rax, ds:2[rax*2]
0x140014f46  jmp     short loc_140014F4B
0x140014f48  mov     rax, rbx
0x140014f4b  lea     edx, [rax+r9]
0x140014f4f  mov     [rdi+4], edx
0x140014f52  mov     rax, [rsi+58h]
0x140014f56  add     rax, 34h ; '4'
0x140014f5a  jz      short loc_140014F70
0x140014f5c  inc     r8
0x140014f5f  cmp     [rax+r8*2], bx
0x140014f64  jnz     short loc_140014F5C
0x140014f66  lea     r8, ds:2[r8*2]
0x140014f6e  jmp     short loc_140014F73
0x140014f70  mov     r8, rbx
0x140014f73  add     edx, r8d
0x140014f76  mov     [rdi+4], edx
0x140014f79  call    cs:__imp_CoTaskMemFree
0x140014f7f  mov     eax, 1
0x140014f84  jmp     loc_14001513E
0x140014f89  cmp     dword ptr [rdx], 2
0x140014f8c  jnz     loc_14001513C
0x140014f92  add     rcx, 20h ; ' '; rclsid
0x140014f96  lea     rdx, [rsp+78h+pv]; lplpsz
0x140014f9e  call    cs:__imp_StringFromIID
0x140014fa4  lea     r14, [rdi+4]
0x140014fa8  mov     [rsp+78h+arg_18], r14
0x140014fb0  lea     r15, [rdi+18h]
0x140014fb4  mov     [rsp+78h+var_40], r15
0x140014fb9  mov     ecx, [r14]
0x140014fbc  shl     rcx, 6
0x140014fc0  mov     rax, [r15]
0x140014fc3  mov     dword ptr [rcx+rax], 40h ; '@'
0x140014fca  lea     r12, [rdi+10h]
0x140014fce  mov     [rsp+78h+var_48], r12
0x140014fd3  mov     rax, [r12]
0x140014fd7  mov     edx, [r14]
0x140014fda  shl     rdx, 6
0x140014fde  mov     rcx, [r15]
0x140014fe1  mov     eax, [rax+18h]
0x140014fe4  mov     [rdx+rcx+4], eax
0x140014fe8  mov     rax, [rsi+58h]
0x140014fec  mov     rdx, [r12]
0x140014ff0  or      r8, 0FFFFFFFFFFFFFFFFh
0x140014ff4  mov     edx, [rdx+18h]
0x140014ff7  mov     rcx, [rsp+78h+pv]
0x140014fff  mov     rax, [rax+678h]
0x140015006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001500b  mov     edx, [r14]
0x14001500e  shl     rdx, 6
0x140015012  mov     rcx, [r15]
0x140015015  mov     [rdx+rcx+8], eax
0x140015019  jmp     short loc_14001503D
0x14001501b  mov     rdi, [rsp+78h+arg_8]
0x140015023  mov     rsi, [rsp+78h+arg_0]
0x14001502b  mov     r14, [rsp+78h+arg_18]
0x140015033  mov     r12, [rsp+78h+var_48]
0x140015038  mov     r15, [rsp+78h+var_40]
0x14001503d  lea     rbx, [rdi+8]
0x140015041  mov     r8, [r15]
0x140015044  mov     eax, [r14]
0x140015047  shl     rax, 6
0x14001504b  lea     rdx, [r8+10h]
0x14001504f  add     rdx, rax
0x140015052  mov     rcx, [r12]
0x140015056  mov     eax, [rdi+20h]
0x140015059  mov     [rsp+78h+var_58], eax; int
0x14001505d  mov     r9, rbx
0x140015060  mov     rcx, [rcx+38h]; unsigned __int16 *
0x140015064  call    StoreString
0x140015069  mov     r8, [r15]
0x14001506c  mov     eax, [r14]
0x14001506f  shl     rax, 6
0x140015073  lea     rdx, [r8+18h]
0x140015077  add     rdx, rax
0x14001507a  mov     eax, [rdi+20h]
0x14001507d  mov     [rsp+78h+var_58], eax; int
0x140015081  mov     r9, rbx
0x140015084  mov     rcx, [rsp+78h+pv]; unsigned __int16 *
0x14001508c  call    StoreString
0x140015091  mov     r8, [r15]
0x140015094  mov     eax, [r14]
0x140015097  shl     rax, 6
0x14001509b  lea     rdx, [r8+20h]
0x14001509f  add     rdx, rax
0x1400150a2  mov     eax, [rdi+20h]
0x1400150a5  mov     [rsp+78h+var_58], eax; int
0x1400150a9  mov     r9, rbx
0x1400150ac  mov     rcx, [rsi+40h]; unsigned __int16 *
0x1400150b0  call    StoreString
0x1400150b5  mov     r8, [r15]
0x1400150b8  mov     eax, [r14]
0x1400150bb  shl     rax, 6
0x1400150bf  lea     rdx, [r8+28h]
0x1400150c3  add     rdx, rax
0x1400150c6  mov     eax, [rdi+20h]
0x1400150c9  mov     [rsp+78h+var_58], eax; int
0x1400150cd  mov     r9, rbx
0x1400150d0  mov     rcx, [rsi+38h]; unsigned __int16 *
0x1400150d4  call    StoreString
0x1400150d9  mov     r8, [r15]
0x1400150dc  mov     eax, [r14]
0x1400150df  shl     rax, 6
0x1400150e3  lea     rdx, [r8+30h]
0x1400150e7  add     rdx, rax
0x1400150ea  mov     rcx, [rsi+58h]
0x1400150ee  add     rcx, 23Ch; unsigned __int16 *
0x1400150f5  mov     eax, [rdi+20h]
0x1400150f8  mov     [rsp+78h+var_58], eax; int
0x1400150fc  mov     r9, rbx
0x1400150ff  call    StoreString
0x140015104  mov     r8, [r15]
0x140015107  mov     eax, [r14]
0x14001510a  shl     rax, 6
0x14001510e  lea     rdx, [r8+38h]
0x140015112  add     rdx, rax
0x140015115  mov     rcx, [rsi+58h]
0x140015119  add     rcx, 34h ; '4'; unsigned __int16 *
0x14001511d  mov     eax, [rdi+20h]
0x140015120  mov     [rsp+78h+var_58], eax; int
0x140015124  mov     r9, rbx
0x140015127  call    StoreString
0x14001512c  inc     dword ptr [r14]
0x14001512f  mov     rcx, [rsp+78h+pv]
0x140015137  jmp     loc_140014F79
0x14001513c  xor     eax, eax
0x14001513e  add     rsp, 48h
0x140015142  pop     r15
0x140015144  pop     r14
0x140015146  pop     r12
0x140015148  pop     rdi
0x140015149  pop     rsi
0x14001514a  pop     rbx
0x14001514b  retn
0x140081e59  push    rbp
0x140081e5b  sub     rsp, 30h
0x140081e5f  mov     rbp, rdx
0x140081e62  mov     r8, [rcx]
0x140081e65  mov     r8d, [r8]
0x140081e68  mov     rax, [rbp+80h]
0x140081e6f  mov     rdx, [rax+58h]
0x140081e73  add     rdx, 34h ; '4'
0x140081e77  mov     ecx, 2
0x140081e7c  call    ?HandleFaxExtensionFault@@YAJW4EXCEPTION_SOURCE_TYPE@@PEBGK@Z; HandleFaxExtensionFault(EXCEPTION_SOURCE_TYPE,ushort const *,ulong)
0x140081e81  nop
0x140081e82  add     rsp, 30h
0x140081e86  pop     rbp
0x140081e87  retn
```
