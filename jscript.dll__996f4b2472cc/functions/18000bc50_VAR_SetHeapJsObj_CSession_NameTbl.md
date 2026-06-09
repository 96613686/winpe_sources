# VAR::SetHeapJsObj(CSession *,NameTbl *)

- ea: `0x18000bc50`
- end: `0x18000bea2`
- name: `?SetHeapJsObj@VAR@@QEAAJPEAVCSession@@PEAVNameTbl@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(VAR *__hidden this, struct CSession *, struct NameTbl *)`
- caller_count: `52`
- callee_count: `9`
- tags: ``

## callers

- `0x180001b30`
- `0x180001e60`
- `0x1800065fc`
- `0x180006b60`
- `0x1800091e4`
- `0x18000990c`
- `0x18000b0e0`
- `0x18000e9e0`
- `0x180011180`
- `0x180013ce0`
- `0x180014da0`
- `0x180015a10`
- `0x180015ee0`
- `0x180023440`
- `0x1800307e0`
- `0x18003cc60`
- `0x18003f330`
- `0x18003f7a0`
- `0x180040870`
- `0x180042b60`
- `0x1800432b0`
- `0x1800439b4`
- `0x180044d20`
- `0x1800457e0`
- `0x180045bc0`
- `0x180047330`
- `0x180047d40`
- `0x18004ae10`
- `0x18004af70`
- `0x18004c5f0`
- `0x18004c980`
- `0x180050080`
- `0x180051c84`
- `0x180058180`
- `0x1800609c0`
- `0x180060af0`
- `0x180061190`
- `0x180061340`
- `0x180061810`
- `0x1800624f0`
- `0x180063000`
- `0x180063200`
- `0x1800634b0`
- `0x180064f10`
- `0x18006a0a0`
- `0x18006a300`
- `0x18006aa70`
- `0x18006b008`
- `0x18006e520`
- `0x18006eee0`

## callees

- `0x180005ce8`
- `0x18000abf8`
- `0x18000bc50`
- `0x18000beb0`
- `0x18000c860`
- `0x18000c8c0`
- `0x180014cd0`
- `0x18003c414`
- `0x180053048`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18000be58`
- `KERNEL32!TlsGetValue` at `0x18000be58`
- `KERNEL32!GetTickCount` at `0x18000bdd8`
- `KERNEL32!GetTickCount` at `0x18000be25`
- `KERNEL32!GetTickCount` at `0x18000bdd8`
- `KERNEL32!GetTickCount` at `0x18000be25`

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
    if ( v16 < dword_1800B5CE4 || GetTickCount() - TickCount <= 0x2710 )
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
0x18000bc50  push    rsi
0x18000bc52  push    rdi
0x18000bc53  push    r15
0x18000bc55  sub     rsp, 20h
0x18000bc59  mov     rax, [r8+20h]
0x18000bc5d  lea     r15, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000bc64  mov     rdi, r8
0x18000bc67  mov     rsi, rcx
0x18000bc6a  cmp     rax, r15
0x18000bc6d  jnz     loc_18000BD6D
0x18000bc73  mov     [rsp+38h+arg_0], rbx
0x18000bc78  mov     [rsp+38h+arg_8], rbp
0x18000bc7d  mov     [rsp+38h+arg_10], r14
0x18000bc82  test    rdx, rdx
0x18000bc85  jz      loc_18000BE52
0x18000bc8b  mov     rbp, [rdx+3E0h]
0x18000bc92  test    rbp, rbp
0x18000bc95  jnz     short loc_18000BCBC
0x18000bc97  mov     rcx, [rdx+50h]; this
0x18000bc9b  test    rcx, rcx
0x18000bc9e  jnz     loc_18000BE90
0x18000bca4  mov     rcx, [rdx+3D8h]; struct ThreadGlobals *
0x18000bcab  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x18000bcb0  mov     rbp, rax
0x18000bcb3  test    rax, rax
0x18000bcb6  jz      loc_18000BE9A
0x18000bcbc  mov     rbx, [rbp+10h]
0x18000bcc0  mov     eax, [rbx+0Ch]
0x18000bcc3  test    al, 1
0x18000bcc5  jnz     loc_18000BE77
0x18000bccb  xor     r14d, r14d
0x18000bcce  cmp     [rbp+20h], r14
0x18000bcd2  jz      loc_18000BDB3
0x18000bcd8  mov     rbx, [rbp+20h]
0x18000bcdc  movsxd  rcx, dword ptr [rbx+8]
0x18000bce0  test    ecx, ecx
0x18000bce2  jle     loc_18000BDCB
0x18000bce8  lea     eax, [rcx-1]
0x18000bceb  lea     rcx, [rcx+rcx*2]
0x18000bcef  mov     [rbx+8], eax
0x18000bcf2  lea     rbx, [rbx+rcx*8]
0x18000bcf6  mov     [rbx], r14w
0x18000bcfa  mov     rbp, [rbp+10h]
0x18000bcfe  mov     r14d, [rbp+98h]
0x18000bd05  test    r14d, r14d
0x18000bd08  jz      loc_18000BE25
0x18000bd0e  inc     dword ptr [rbp+68h]
0x18000bd11  inc     dword ptr [rbp+74h]
0x18000bd14  cmp     dword ptr [rbp+8], 0
0x18000bd18  mov     eax, [rbp+68h]
0x18000bd1b  jnz     short loc_18000BD32
0x18000bd1d  cmp     eax, [rbp+78h]
0x18000bd20  jge     loc_18000BE3F
0x18000bd26  cmp     eax, cs:dword_1800B5CE4
0x18000bd2c  jge     loc_18000BDD8
0x18000bd32  mov     word ptr [rbx], 81h
0x18000bd37  mov     [rbx+8], rdi
0x18000bd3b  cmp     [rdi+20h], r15
0x18000bd3f  jz      short loc_18000BD8B
0x18000bd41  mov     rbp, [rdi+48h]
0x18000bd45  lock inc dword ptr [rbp+0]
0x18000bd49  lea     rcx, [rbp+38h]; this
0x18000bd4d  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000bd52  test    eax, eax
0x18000bd54  jz      short loc_18000BD63
0x18000bd56  lea     rcx, [rbp+38h]; this
0x18000bd5a  mov     [rdi+20h], rbx
0x18000bd5e  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000bd63  mov     rcx, rbp; this
0x18000bd66  call    ?Release@GcContext@@QEAAJXZ; GcContext::Release(void)
0x18000bd6b  jmp     short loc_18000BD8F
0x18000bd6d  test    rax, rax
0x18000bd70  jz      loc_18000BC73
0x18000bd76  mov     [rcx+8], rax
0x18000bd7a  xor     eax, eax
0x18000bd7c  mov     word ptr [rcx], 80h
0x18000bd81  add     rsp, 20h
0x18000bd85  pop     r15
0x18000bd87  pop     rdi
0x18000bd88  pop     rsi
0x18000bd89  retn
0x18000bd8b  mov     [rdi+20h], rbx
0x18000bd8f  mov     word ptr [rsi], 80h
0x18000bd94  xor     eax, eax
0x18000bd96  mov     [rsi+8], rbx
0x18000bd9a  mov     rbp, [rsp+38h+arg_8]
0x18000bd9f  mov     rbx, [rsp+38h+arg_0]
0x18000bda4  mov     r14, [rsp+38h+arg_10]
0x18000bda9  add     rsp, 20h
0x18000bdad  pop     r15
0x18000bdaf  pop     rdi
0x18000bdb0  pop     rsi
0x18000bdb1  retn
0x18000bdb3  call    ?PblkAlloc@GcBlockFactory@@QEAAPEAVGcBlock@@XZ; GcBlockFactory::PblkAlloc(void)
0x18000bdb8  mov     r9, rax
0x18000bdbb  test    rax, rax
0x18000bdbe  jnz     short loc_18000BDFB
0x18000bdc0  mov     [rsi], r14w
0x18000bdc4  mov     eax, 8007000Eh
0x18000bdc9  jmp     short loc_18000BD9A
0x18000bdcb  mov     rax, [rbx+10h]
0x18000bdcf  mov     [rbp+20h], rax
0x18000bdd3  jmp     loc_18000BCF6
0x18000bdd8  call    cs:__imp_GetTickCount
0x18000bddf  nop     dword ptr [rax+rax+00h]
0x18000bde4  sub     eax, r14d
0x18000bde7  cmp     eax, 2710h
0x18000bdec  jbe     loc_18000BD32
0x18000bdf2  and     dword ptr [rbp+9Ch], 0FFFFFFFEh
0x18000bdf9  jmp     short loc_18000BE46
0x18000bdfb  lea     rdx, [rbp+18h]; struct GcBlock **
0x18000bdff  mov     rcx, r9; this
0x18000be02  call    ?Link@GcBlock@@QEAAXPEAPEAV1@@Z; GcBlock::Link(GcBlock * *)
0x18000be07  lea     rcx, [r9+10h]
0x18000be0b  mov     [rbp+20h], rcx
0x18000be0f  mov     word ptr [rcx], 8Ah
0x18000be14  mov     dword ptr [r9+18h], 63h ; 'c'
0x18000be1c  mov     [r9+20h], r14
0x18000be20  jmp     loc_18000BCD8
0x18000be25  call    cs:__imp_GetTickCount
0x18000be2c  nop     dword ptr [rax+rax+00h]
0x18000be31  mov     r14d, eax
0x18000be34  mov     [rbp+98h], eax
0x18000be3a  jmp     loc_18000BD0E
0x18000be3f  or      dword ptr [rbp+9Ch], 1
0x18000be46  mov     dword ptr [rbp+8], 1
0x18000be4d  jmp     loc_18000BD32
0x18000be52  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18000be58  call    cs:__imp_TlsGetValue
0x18000be5f  nop     dword ptr [rax+rax+00h]
0x18000be64  mov     rcx, rax; struct ThreadGlobals *
0x18000be67  call    ?GetAllocator@GcAlloc@@SAPEAV1@PEAVThreadGlobals@@@Z; GcAlloc::GetAllocator(ThreadGlobals *)
0x18000be6c  mov     rbp, rax
0x18000be6f  test    rax, rax
0x18000be72  jmp     loc_18000BCB6
0x18000be77  test    al, 2
0x18000be79  jnz     loc_18000BCCB
0x18000be7f  mov     rcx, rbx; this
0x18000be82  call    ?ClearMark@GcContext@@QEAAXXZ; GcContext::ClearMark(void)
0x18000be87  or      dword ptr [rbx+0Ch], 2
0x18000be8b  jmp     loc_18000BCCB
0x18000be90  call    ?GetGcAlloc@CScriptRuntime@@QEAAPEAVGcAlloc@@XZ; CScriptRuntime::GetGcAlloc(void)
0x18000be95  jmp     loc_18000BCB0
0x18000be9a  xor     r14d, r14d
0x18000be9d  jmp     loc_18000BDC0
```
