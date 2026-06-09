# VAR::SetHeapJsObj(CSession *,NameTbl *)

- ea: `0x18000ea20`
- end: `0x18000ec5e`
- name: `?SetHeapJsObj@VAR@@QEAAJPEAVCSession@@PEAVNameTbl@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(VAR *__hidden this, struct CSession *, struct NameTbl *)`
- caller_count: `52`
- callee_count: `9`
- tags: ``

## callers

- `0x180001e40`
- `0x18000c05c`
- `0x18000c778`
- `0x18000ded0`
- `0x1800117b0`
- `0x180014b50`
- `0x180016d10`
- `0x180017ee0`
- `0x180018b40`
- `0x180018ef0`
- `0x180026230`
- `0x1800327e0`
- `0x1800385e0`
- `0x180038910`
- `0x18003ad20`
- `0x18003c190`
- `0x1800400f0`
- `0x1800406e0`
- `0x1800415b0`
- `0x180042794`
- `0x180043a80`
- `0x1800443ac`
- `0x180044b50`
- `0x180044f30`
- `0x180046600`
- `0x180047020`
- `0x18004a010`
- `0x18004a220`
- `0x18004b450`
- `0x18004b9c0`
- `0x18004bd30`
- `0x18004f000`
- `0x180050f1c`
- `0x180057250`
- `0x18005f7c0`
- `0x18005f8e0`
- `0x18005ff70`
- `0x180060120`
- `0x1800605f0`
- `0x1800612d0`
- `0x180061dc0`
- `0x180061fc0`
- `0x18006225c`
- `0x180063c00`
- `0x180068d60`
- `0x180068fc0`
- `0x180069730`
- `0x180069cc8`
- `0x18006d190`
- `0x18006db48`

## callees

- `0x18000d9fc`
- `0x18000ea20`
- `0x18000ec70`
- `0x18000f5e0`
- `0x18000f630`
- `0x180032b08`
- `0x180033780`
- `0x18003493c`
- `0x1800522b0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18000ec1a`
- `KERNEL32!TlsGetValue` at `0x18000ec1a`
- `KERNEL32!GetTickCount` at `0x18000eba6`
- `KERNEL32!GetTickCount` at `0x18000ebed`
- `KERNEL32!GetTickCount` at `0x18000eba6`
- `KERNEL32!GetTickCount` at `0x18000ebed`

## pseudocode

```c
__int64 __fastcall VAR::SetHeapJsObj(VAR *this, struct CSession *a2, struct NameTbl *a3)
{
  __int64 *v3; // rax
  struct GcAlloc *Allocator; // rbp
  CScriptRuntime *v7; // rcx
  struct GcAlloc *GcAlloc; // rax
  bool v9; // zf
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rbx
  __int64 v13; // rcx
  _DWORD *v14; // rbp
  DWORD TickCount; // r14d
  int v16; // eax
  volatile signed __int32 *v17; // rbp
  __int64 result; // rax
  GcBlock *v19; // rax
  __int64 v20; // r9
  struct ThreadGlobals *Value; // rax

  v3 = (__int64 *)*((_QWORD *)a3 + 4);
  if ( v3 != NameTbl::s_varNameTblConstructed && v3 )
  {
    *((_QWORD *)this + 1) = v3;
    result = 0;
    *(_WORD *)this = 128;
    return result;
  }
  if ( a2 )
  {
    Allocator = (struct GcAlloc *)*((_QWORD *)a2 + 124);
    if ( Allocator )
      goto LABEL_8;
    v7 = (CScriptRuntime *)*((_QWORD *)a2 + 10);
    if ( v7 )
      GcAlloc = CScriptRuntime::GetGcAlloc(v7);
    else
      GcAlloc = GcAlloc::GetAllocator(*((struct ThreadGlobals **)a2 + 123));
    Allocator = GcAlloc;
    v9 = GcAlloc == 0;
  }
  else
  {
    Value = (struct ThreadGlobals *)TlsGetValue(g_luTls);
    Allocator = GcAlloc::GetAllocator(Value);
    v9 = Allocator == 0;
  }
  if ( v9 )
    goto LABEL_26;
LABEL_8:
  v10 = *((_QWORD *)Allocator + 2);
  v11 = *(_DWORD *)(v10 + 12);
  if ( (v11 & 1) != 0 && (v11 & 2) == 0 )
  {
    GcContext::ClearMark(*((GcContext **)Allocator + 2));
    *(_DWORD *)(v10 + 12) |= 2u;
  }
  if ( !*((_QWORD *)Allocator + 4) )
  {
    v19 = GcBlockFactory::PblkAlloc(this);
    if ( v19 )
    {
      GcBlock::Link(v19, (struct GcBlock **)Allocator + 3);
      *((_QWORD *)Allocator + 4) = v20 + 16;
      *(_WORD *)(v20 + 16) = 138;
      *(_DWORD *)(v20 + 24) = 99;
      *(_QWORD *)(v20 + 32) = 0;
      goto LABEL_10;
    }
LABEL_26:
    *(_WORD *)this = 0;
    return 2147942414LL;
  }
LABEL_10:
  v12 = *((_QWORD *)Allocator + 4);
  v13 = *(int *)(v12 + 8);
  if ( (int)v13 <= 0 )
  {
    *((_QWORD *)Allocator + 4) = *(_QWORD *)(v12 + 16);
  }
  else
  {
    *(_DWORD *)(v12 + 8) = v13 - 1;
    v12 += 24 * v13;
  }
  *(_WORD *)v12 = 0;
  v14 = (_DWORD *)*((_QWORD *)Allocator + 2);
  TickCount = v14[38];
  if ( !TickCount )
  {
    TickCount = GetTickCount();
    v14[38] = TickCount;
  }
  ++v14[26];
  ++v14[29];
  v16 = v14[26];
  if ( v14[2] )
    goto LABEL_17;
  if ( v16 >= v14[30] )
  {
    v14[39] |= 1u;
  }
  else
  {
    if ( v16 < dword_1800B3CE4 || GetTickCount() - TickCount <= 0x2710 )
      goto LABEL_17;
    v14[39] &= ~1u;
  }
  v14[2] = 1;
LABEL_17:
  *(_WORD *)v12 = 129;
  *(_QWORD *)(v12 + 8) = a3;
  if ( *((__int64 **)a3 + 4) == NameTbl::s_varNameTblConstructed )
  {
    *((_QWORD *)a3 + 4) = v12;
  }
  else
  {
    v17 = (volatile signed __int32 *)*((_QWORD *)a3 + 9);
    _InterlockedIncrement(v17);
    if ( (unsigned int)MUTX::Enter((MUTX *)(v17 + 14)) )
    {
      *((_QWORD *)a3 + 4) = v12;
      MUTX::Leave((MUTX *)(v17 + 14));
    }
    GcContext::Release((GcContext *)v17);
  }
  *(_WORD *)this = 128;
  result = 0;
  *((_QWORD *)this + 1) = v12;
  return result;
}

```

## disassembly

```asm
0x18000ea20  push    rsi
0x18000ea22  push    rdi
0x18000ea23  push    r15
0x18000ea25  sub     rsp, 20h
0x18000ea29  mov     rax, [r8+20h]
0x18000ea2d  lea     r15, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000ea34  mov     rdi, r8
0x18000ea37  mov     rsi, rcx
0x18000ea3a  cmp     rax, r15
0x18000ea3d  jnz     loc_18000EB3D
0x18000ea43  mov     [rsp+38h+arg_0], rbx
0x18000ea48  mov     [rsp+38h+arg_8], rbp
0x18000ea4d  mov     [rsp+38h+arg_10], r14
0x18000ea52  test    rdx, rdx
0x18000ea55  jz      loc_18000EC14
0x18000ea5b  mov     rbp, [rdx+3E0h]
0x18000ea62  test    rbp, rbp
0x18000ea65  jnz     short loc_18000EA8C
0x18000ea67  mov     rcx, [rdx+50h]; this
0x18000ea6b  test    rcx, rcx
0x18000ea6e  jnz     loc_18000EC4C
0x18000ea74  mov     rcx, [rdx+3D8h]; struct ThreadGlobals *
0x18000ea7b  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x18000ea80  mov     rbp, rax
0x18000ea83  test    rax, rax
0x18000ea86  jz      loc_18000EC56
0x18000ea8c  mov     rbx, [rbp+10h]
0x18000ea90  mov     eax, [rbx+0Ch]
0x18000ea93  test    al, 1
0x18000ea95  jnz     loc_18000EC33
0x18000ea9b  xor     r14d, r14d
0x18000ea9e  cmp     [rbp+20h], r14
0x18000eaa2  jz      loc_18000EB81
0x18000eaa8  mov     rbx, [rbp+20h]
0x18000eaac  movsxd  rcx, dword ptr [rbx+8]
0x18000eab0  test    ecx, ecx
0x18000eab2  jle     loc_18000EB99
0x18000eab8  lea     eax, [rcx-1]
0x18000eabb  lea     rcx, [rcx+rcx*2]
0x18000eabf  mov     [rbx+8], eax
0x18000eac2  lea     rbx, [rbx+rcx*8]
0x18000eac6  mov     [rbx], r14w
0x18000eaca  mov     rbp, [rbp+10h]
0x18000eace  mov     r14d, [rbp+98h]
0x18000ead5  test    r14d, r14d
0x18000ead8  jz      loc_18000EBED
0x18000eade  inc     dword ptr [rbp+68h]
0x18000eae1  inc     dword ptr [rbp+74h]
0x18000eae4  cmp     dword ptr [rbp+8], 0
0x18000eae8  mov     eax, [rbp+68h]
0x18000eaeb  jnz     short loc_18000EB02
0x18000eaed  cmp     eax, [rbp+78h]
0x18000eaf0  jge     loc_18000EC01
0x18000eaf6  cmp     eax, cs:dword_1800B3CE4
0x18000eafc  jge     loc_18000EBA6
0x18000eb02  mov     word ptr [rbx], 81h
0x18000eb07  mov     [rbx+8], rdi
0x18000eb0b  cmp     [rdi+20h], r15
0x18000eb0f  jz      short loc_18000EB5A
0x18000eb11  mov     rbp, [rdi+48h]
0x18000eb15  lock inc dword ptr [rbp+0]
0x18000eb19  lea     rcx, [rbp+38h]; this
0x18000eb1d  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000eb22  test    eax, eax
0x18000eb24  jz      short loc_18000EB33
0x18000eb26  lea     rcx, [rbp+38h]; this
0x18000eb2a  mov     [rdi+20h], rbx
0x18000eb2e  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000eb33  mov     rcx, rbp; this
0x18000eb36  call    ?Release@GcContext@@QEAAJXZ; GcContext::Release(void)
0x18000eb3b  jmp     short loc_18000EB5E
0x18000eb3d  test    rax, rax
0x18000eb40  jz      loc_18000EA43
0x18000eb46  mov     [rcx+8], rax
0x18000eb4a  xor     eax, eax
0x18000eb4c  mov     word ptr [rcx], 80h
0x18000eb51  add     rsp, 20h
0x18000eb55  pop     r15
0x18000eb57  pop     rdi
0x18000eb58  pop     rsi
0x18000eb59  retn
0x18000eb5a  mov     [rdi+20h], rbx
0x18000eb5e  mov     word ptr [rsi], 80h
0x18000eb63  xor     eax, eax
0x18000eb65  mov     [rsi+8], rbx
0x18000eb69  mov     rbp, [rsp+38h+arg_8]
0x18000eb6e  mov     rbx, [rsp+38h+arg_0]
0x18000eb73  mov     r14, [rsp+38h+arg_10]
0x18000eb78  add     rsp, 20h
0x18000eb7c  pop     r15
0x18000eb7e  pop     rdi
0x18000eb7f  pop     rsi
0x18000eb80  retn
0x18000eb81  call    ?PblkAlloc@GcBlockFactory@@QEAAPEAVGcBlock@@XZ; GcBlockFactory::PblkAlloc(void)
0x18000eb86  mov     r9, rax
0x18000eb89  test    rax, rax
0x18000eb8c  jnz     short loc_18000EBC3
0x18000eb8e  mov     [rsi], r14w
0x18000eb92  mov     eax, 8007000Eh
0x18000eb97  jmp     short loc_18000EB69
0x18000eb99  mov     rax, [rbx+10h]
0x18000eb9d  mov     [rbp+20h], rax
0x18000eba1  jmp     loc_18000EAC6
0x18000eba6  call    cs:__imp_GetTickCount
0x18000ebac  sub     eax, r14d
0x18000ebaf  cmp     eax, 2710h
0x18000ebb4  jbe     loc_18000EB02
0x18000ebba  and     dword ptr [rbp+9Ch], 0FFFFFFFEh
0x18000ebc1  jmp     short loc_18000EC08
0x18000ebc3  lea     rdx, [rbp+18h]; struct GcBlock **
0x18000ebc7  mov     rcx, r9; this
0x18000ebca  call    ?Link@GcBlock@@QEAAXPEAPEAV1@@Z; GcBlock::Link(GcBlock * *)
0x18000ebcf  lea     rcx, [r9+10h]
0x18000ebd3  mov     [rbp+20h], rcx
0x18000ebd7  mov     word ptr [rcx], 8Ah
0x18000ebdc  mov     dword ptr [r9+18h], 63h ; 'c'
0x18000ebe4  mov     [r9+20h], r14
0x18000ebe8  jmp     loc_18000EAA8
0x18000ebed  call    cs:__imp_GetTickCount
0x18000ebf3  mov     r14d, eax
0x18000ebf6  mov     [rbp+98h], eax
0x18000ebfc  jmp     loc_18000EADE
0x18000ec01  or      dword ptr [rbp+9Ch], 1
0x18000ec08  mov     dword ptr [rbp+8], 1
0x18000ec0f  jmp     loc_18000EB02
0x18000ec14  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18000ec1a  call    cs:__imp_TlsGetValue
0x18000ec20  mov     rcx, rax; struct ThreadGlobals *
0x18000ec23  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x18000ec28  mov     rbp, rax
0x18000ec2b  test    rax, rax
0x18000ec2e  jmp     loc_18000EA86
0x18000ec33  test    al, 2
0x18000ec35  jnz     loc_18000EA9B
0x18000ec3b  mov     rcx, rbx; this
0x18000ec3e  call    ?ClearMark@GcContext@@QEAAXXZ; GcContext::ClearMark(void)
0x18000ec43  or      dword ptr [rbx+0Ch], 2
0x18000ec47  jmp     loc_18000EA9B
0x18000ec4c  call    ?GetGcAlloc@CScriptRuntime@@QEAAPEAVGcAlloc@@XZ; CScriptRuntime::GetGcAlloc(void)
0x18000ec51  jmp     loc_18000EA80
0x18000ec56  xor     r14d, r14d
0x18000ec59  jmp     loc_18000EB8E
```
