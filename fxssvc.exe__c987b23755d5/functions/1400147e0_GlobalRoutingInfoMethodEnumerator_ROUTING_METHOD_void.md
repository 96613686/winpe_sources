# GlobalRoutingInfoMethodEnumerator(_ROUTING_METHOD *,void *)

- ea: `0x1400147e0`
- end: `0x140014a41`
- name: `?GlobalRoutingInfoMethodEnumerator@@YAHPEAU_ROUTING_METHOD@@PEAX@Z`
- size: `609`
- prototype: `__int64 __fastcall(struct _ROUTING_METHOD *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1400147e0`
- `0x1400670fc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400148f3`
- `ole32!CoTaskMemFree` at `0x1400148f3`
- `ole32!StringFromIID` at `0x140014811`
- `ole32!StringFromIID` at `0x140014915`
- `ole32!StringFromIID` at `0x140014811`
- `ole32!StringFromIID` at `0x140014915`

## pseudocode

```c
__int64 __fastcall GlobalRoutingInfoMethodEnumerator(struct _ROUTING_METHOD *a1, unsigned int *a2)
{
  bool v3; // zf
  LPVOID v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // edx
  unsigned int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  int v13; // r10d
  __int64 v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  int v17; // r9d
  __int64 v18; // rax
  int v19; // eax
  int v20; // ecx
  unsigned int v21; // edx
  void *v22; // rcx
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF

  v3 = *a2 == 1;
  pv = 0;
  if ( v3 )
  {
    a2[1] += 48;
    StringFromIID((const IID *const)a1 + 2, (LPOLESTR *)&pv);
    v5 = pv;
    v6 = -1;
    if ( pv )
    {
      v7 = -1;
      do
        ++v7;
      while ( *((_WORD *)pv + v7) );
      v8 = 2 * v7 + 2;
    }
    else
    {
      v8 = 0;
    }
    v9 = v8 + a2[1];
    a2[1] = v9;
    v10 = *((_QWORD *)a1 + 7);
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      v12 = 2 * v11 + 2;
    }
    else
    {
      v12 = 0;
    }
    v13 = v12 + v9;
    a2[1] = v12 + v9;
    v14 = *((_QWORD *)a1 + 8);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v16 = 0;
    }
    v17 = v16 + v13;
    a2[1] = v16 + v13;
    if ( *((_QWORD *)a1 + 11) == -572 )
    {
      v19 = 0;
    }
    else
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(*((_QWORD *)a1 + 11) + 572LL + 2 * v18) );
      v19 = 2 * v18 + 2;
    }
    a2[1] = v19 + v17;
    if ( *((_QWORD *)a1 + 11) == -52 )
    {
      v20 = 0;
    }
    else
    {
      do
        ++v6;
      while ( *(_WORD *)(*((_QWORD *)a1 + 11) + 52LL + 2 * v6) );
      v20 = 2 * v6 + 2;
    }
    v21 = v20 + v19 + v17;
    v22 = v5;
    a2[1] = v21;
    goto LABEL_27;
  }
  if ( *a2 == 2 )
  {
    StringFromIID((const IID *const)a1 + 2, (LPOLESTR *)&pv);
    *(_DWORD *)(*((_QWORD *)a2 + 2) + 48LL * a2[1]) = 48;
    *(_DWORD *)(*((_QWORD *)a2 + 2) + 48LL * a2[1] + 4) = *((_DWORD *)a1 + 12);
    StoreString((unsigned __int16 *)pv, a2[6]);
    StoreString(*((unsigned __int16 **)a1 + 8), a2[6]);
    StoreString(*((unsigned __int16 **)a1 + 7), a2[6]);
    StoreString((unsigned __int16 *)(*((_QWORD *)a1 + 11) + 572LL), a2[6]);
    StoreString((unsigned __int16 *)(*((_QWORD *)a1 + 11) + 52LL), a2[6]);
    ++a2[1];
    v22 = pv;
LABEL_27:
    CoTaskMemFree(v22);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1400147e0  mov     rax, rsp
0x1400147e3  mov     [rax+8], rbx
0x1400147e7  mov     [rax+18h], rsi
0x1400147eb  push    rdi
0x1400147ec  sub     rsp, 30h
0x1400147f0  xor     ebx, ebx
0x1400147f2  mov     rdi, rdx
0x1400147f5  cmp     dword ptr [rdx], 1
0x1400147f8  mov     rsi, rcx
0x1400147fb  mov     [rax+10h], rbx
0x1400147ff  jnz     loc_140014903
0x140014805  add     dword ptr [rdx+4], 30h ; '0'
0x140014809  add     rcx, 20h ; ' '; rclsid
0x14001480d  lea     rdx, [rax+10h]; lplpsz
0x140014811  call    cs:__imp_StringFromIID
0x140014817  mov     r8, [rsp+38h+pv]
0x14001481c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140014820  test    r8, r8
0x140014823  jz      short loc_14001483C
0x140014825  mov     rax, rcx
0x140014828  inc     rax
0x14001482b  cmp     [r8+rax*2], bx
0x140014830  jnz     short loc_140014828
0x140014832  lea     rdx, ds:2[rax*2]
0x14001483a  jmp     short loc_14001483F
0x14001483c  mov     rdx, rbx
0x14001483f  mov     r9d, [rdi+4]
0x140014843  add     r9d, edx
0x140014846  mov     [rdi+4], r9d
0x14001484a  mov     rdx, [rsi+38h]
0x14001484e  test    rdx, rdx
0x140014851  jz      short loc_140014869
0x140014853  mov     rax, rcx
0x140014856  inc     rax
0x140014859  cmp     [rdx+rax*2], bx
0x14001485d  jnz     short loc_140014856
0x14001485f  lea     rax, ds:2[rax*2]
0x140014867  jmp     short loc_14001486C
0x140014869  mov     rax, rbx
0x14001486c  lea     r10d, [rax+r9]
0x140014870  mov     [rdi+4], r10d
0x140014874  mov     rdx, [rsi+40h]
0x140014878  test    rdx, rdx
0x14001487b  jz      short loc_140014893
0x14001487d  mov     rax, rcx
0x140014880  inc     rax
0x140014883  cmp     [rdx+rax*2], bx
0x140014887  jnz     short loc_140014880
0x140014889  lea     rax, ds:2[rax*2]
0x140014891  jmp     short loc_140014896
0x140014893  mov     rax, rbx
0x140014896  lea     r9d, [rax+r10]
0x14001489a  mov     [rdi+4], r9d
0x14001489e  mov     rdx, [rsi+58h]
0x1400148a2  add     rdx, 23Ch
0x1400148a9  jz      short loc_1400148C1
0x1400148ab  mov     rax, rcx
0x1400148ae  inc     rax
0x1400148b1  cmp     [rdx+rax*2], bx
0x1400148b5  jnz     short loc_1400148AE
0x1400148b7  lea     rax, ds:2[rax*2]
0x1400148bf  jmp     short loc_1400148C4
0x1400148c1  mov     rax, rbx
0x1400148c4  lea     edx, [rax+r9]
0x1400148c8  mov     [rdi+4], edx
0x1400148cb  mov     rax, [rsi+58h]
0x1400148cf  add     rax, 34h ; '4'
0x1400148d3  jz      short loc_1400148E8
0x1400148d5  inc     rcx
0x1400148d8  cmp     [rax+rcx*2], bx
0x1400148dc  jnz     short loc_1400148D5
0x1400148de  lea     rcx, ds:2[rcx*2]
0x1400148e6  jmp     short loc_1400148EB
0x1400148e8  mov     rcx, rbx
0x1400148eb  add     edx, ecx
0x1400148ed  mov     rcx, r8; pv
0x1400148f0  mov     [rdi+4], edx
0x1400148f3  call    cs:__imp_CoTaskMemFree
0x1400148f9  mov     eax, 1
0x1400148fe  jmp     loc_140014A31
0x140014903  cmp     dword ptr [rdx], 2
0x140014906  jnz     loc_140014A2F
0x14001490c  add     rcx, 20h ; ' '; rclsid
0x140014910  lea     rdx, [rsp+38h+pv]; lplpsz
0x140014915  call    cs:__imp_StringFromIID
0x14001491b  mov     eax, [rdi+4]
0x14001491e  lea     rbx, [rdi+8]
0x140014922  mov     r9, rbx
0x140014925  lea     rcx, [rax+rax*2]
0x140014929  mov     rax, [rdi+10h]
0x14001492d  add     rcx, rcx
0x140014930  mov     dword ptr [rax+rcx*8], 30h ; '0'
0x140014937  mov     eax, [rdi+4]
0x14001493a  mov     rcx, [rdi+10h]
0x14001493e  lea     rdx, [rax+rax*2]
0x140014942  mov     eax, [rsi+30h]
0x140014945  add     rdx, rdx
0x140014948  mov     [rcx+rdx*8+4], eax
0x14001494c  mov     eax, [rdi+4]
0x14001494f  mov     r8, [rdi+10h]
0x140014953  lea     rcx, [rax+rax*2]
0x140014957  mov     eax, [rdi+18h]
0x14001495a  shl     rcx, 4
0x14001495e  lea     rdx, [r8+8]
0x140014962  add     rdx, rcx
0x140014965  mov     [rsp+38h+var_18], eax; int
0x140014969  mov     rcx, [rsp+38h+pv]; unsigned __int16 *
0x14001496e  call    StoreString
0x140014973  mov     eax, [rdi+4]
0x140014976  mov     r9, rbx
0x140014979  mov     r8, [rdi+10h]
0x14001497d  lea     rcx, [rax+rax*2]
0x140014981  mov     eax, [rdi+18h]
0x140014984  shl     rcx, 4
0x140014988  lea     rdx, [r8+10h]
0x14001498c  add     rdx, rcx
0x14001498f  mov     [rsp+38h+var_18], eax; int
0x140014993  mov     rcx, [rsi+40h]; unsigned __int16 *
0x140014997  call    StoreString
0x14001499c  mov     eax, [rdi+4]
0x14001499f  mov     r9, rbx
0x1400149a2  mov     r8, [rdi+10h]
0x1400149a6  lea     rcx, [rax+rax*2]
0x1400149aa  mov     eax, [rdi+18h]
0x1400149ad  shl     rcx, 4
0x1400149b1  lea     rdx, [r8+18h]
0x1400149b5  add     rdx, rcx
0x1400149b8  mov     [rsp+38h+var_18], eax; int
0x1400149bc  mov     rcx, [rsi+38h]; unsigned __int16 *
0x1400149c0  call    StoreString
0x1400149c5  mov     eax, [rdi+4]
0x1400149c8  mov     r9, rbx
0x1400149cb  mov     r8, [rdi+10h]
0x1400149cf  lea     rcx, [rax+rax*2]
0x1400149d3  mov     eax, [rdi+18h]
0x1400149d6  shl     rcx, 4
0x1400149da  lea     rdx, [r8+20h]
0x1400149de  add     rdx, rcx
0x1400149e1  mov     [rsp+38h+var_18], eax; int
0x1400149e5  mov     rcx, [rsi+58h]
0x1400149e9  add     rcx, 23Ch; unsigned __int16 *
0x1400149f0  call    StoreString
0x1400149f5  mov     eax, [rdi+4]
0x1400149f8  mov     r9, rbx
0x1400149fb  mov     r8, [rdi+10h]
0x1400149ff  lea     rcx, [rax+rax*2]
0x140014a03  mov     eax, [rdi+18h]
0x140014a06  shl     rcx, 4
0x140014a0a  lea     rdx, [r8+28h]
0x140014a0e  add     rdx, rcx
0x140014a11  mov     [rsp+38h+var_18], eax; int
0x140014a15  mov     rcx, [rsi+58h]
0x140014a19  add     rcx, 34h ; '4'; unsigned __int16 *
0x140014a1d  call    StoreString
0x140014a22  inc     dword ptr [rdi+4]
0x140014a25  mov     rcx, [rsp+38h+pv]
0x140014a2a  jmp     loc_1400148F3
0x140014a2f  xor     eax, eax
0x140014a31  mov     rbx, [rsp+38h+arg_0]
0x140014a36  mov     rsi, [rsp+38h+arg_10]
0x140014a3b  add     rsp, 30h
0x140014a3f  pop     rdi
0x140014a40  retn
```
