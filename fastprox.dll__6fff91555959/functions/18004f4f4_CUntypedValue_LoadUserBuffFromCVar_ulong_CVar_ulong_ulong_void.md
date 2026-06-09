# CUntypedValue::LoadUserBuffFromCVar(ulong,CVar *,ulong,ulong *,void *)

- ea: `0x18004f4f4`
- end: `0x18004f6ea`
- name: `?LoadUserBuffFromCVar@CUntypedValue@@SAJKPEAVCVar@@KPEAKPEAX@Z`
- size: `502`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, struct CVar *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, void *)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004f260`
- `0x180050080`
- `0x18007dab0`
- `0x18007dce0`

## callees

- `0x1800088d0`
- `0x180037120`
- `0x18004f4f4`
- `0x18004f6f0`
- `0x18004f730`
- `0x18004f9a0`
- `0x18006fa66`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004f6d4`
- `wbemcomn!GetMemLogObject` at `0x18004f6d4`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x18004f531`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x18004f574`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x18004f531`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x18004f574`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18004f5d6`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18004f624`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18004f5d6`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18004f624`
- `wbemcomn!ReadI64` at `0x18004f632`
- `wbemcomn!ReadI64` at `0x18004f632`
- `wbemcomn!ReadUI64` at `0x18004f5e4`
- `wbemcomn!ReadUI64` at `0x18004f5e4`
- `wbemcomn!?GetUnknown@CVar@@QEAAPEAUIUnknown@@XZ` at `0x18004f6c4`
- `wbemcomn!?GetUnknown@CVar@@QEAAPEAUIUnknown@@XZ` at `0x18004f6c4`
- `wbemcomn!?GetRawData@CVar@@QEAAPEAXXZ` at `0x18004f661`
- `wbemcomn!?GetRawData@CVar@@QEAAPEAXXZ` at `0x18004f661`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004f6df`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004f6df`

## pseudocode

```c
__int64 __fastcall CUntypedValue::LoadUserBuffFromCVar(
        unsigned int a1,
        struct CVar *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned __int16 *a5)
{
  unsigned int v6; // ebp
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // esi
  const unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rax
  int I64; // eax
  struct IUnknown *Unknown; // rax
  const unsigned __int16 *LPWSTR; // rax
  unsigned int Length; // eax
  unsigned int v21; // ebx
  const void *RawData; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v24[9]; // [rsp+20h] [rbp-48h] BYREF

  v6 = 0;
  if ( (unsigned int)CType::IsNonArrayPointerType(a1) )
  {
    if ( (unsigned int)CType::IsStringType(a1) )
    {
      v10 = CVar::operator unsigned short *(a2);
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      v12 = 2 * v11 + 2;
      *a4 = v12;
      if ( a3 >= v12 && a5 )
      {
        v14 = (const unsigned __int16 *)CVar::operator unsigned short *(a2);
        StringCchCopyW(a5, v12, v14);
        goto LABEL_9;
      }
      return 2147749948LL;
    }
    *a4 = 8;
    if ( a3 < 8 )
      return 2147749948LL;
    v15 = a5;
    if ( !a5 )
      return 2147749948LL;
    Unknown = CVar::GetUnknown(a2);
    goto LABEL_19;
  }
  if ( a1 == 20 )
  {
    *a4 = 8;
    if ( a3 < 8 )
      return 2147749948LL;
    v15 = a5;
    if ( !a5 )
      return 2147749948LL;
    v24[0] = 0;
    LPWSTR = CVar::GetLPWSTR(a2);
    I64 = ReadI64(LPWSTR, v24);
  }
  else
  {
    if ( a1 != 21 )
    {
      Length = CType::GetLength(a1);
      *a4 = Length;
      if ( a3 < Length || !a5 )
        return 2147749948LL;
      v21 = Length;
      RawData = CVar::GetRawData(a2);
      memcpy_0(a5, RawData, v21);
      goto LABEL_9;
    }
    *a4 = 8;
    if ( a3 < 8 )
      return 2147749948LL;
    v15 = a5;
    if ( !a5 )
      return 2147749948LL;
    v24[0] = 0;
    v16 = CVar::GetLPWSTR(a2);
    I64 = ReadUI64(v16, (unsigned __int64 *)v24);
  }
  if ( I64 )
  {
    Unknown = (struct IUnknown *)v24[0];
LABEL_19:
    *(_QWORD *)v15 = Unknown;
    goto LABEL_9;
  }
  v6 = -2147217378;
  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, -2147217378);
LABEL_9:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18004f4f4  push    rbx
0x18004f4f6  push    rbp
0x18004f4f7  push    rsi
0x18004f4f8  push    rdi
0x18004f4f9  push    r14
0x18004f4fb  push    r15
0x18004f4fd  sub     rsp, 38h
0x18004f501  xor     r15d, r15d
0x18004f504  mov     rbx, r9
0x18004f507  mov     ebp, r15d
0x18004f50a  mov     edi, r8d
0x18004f50d  mov     r14, rdx
0x18004f510  mov     esi, ecx
0x18004f512  call    ?IsNonArrayPointerType@CType@@SAHK@Z; CType::IsNonArrayPointerType(ulong)
0x18004f517  test    eax, eax
0x18004f519  jz      loc_18004F5A8
0x18004f51f  mov     ecx, esi; unsigned int
0x18004f521  call    ?IsStringType@CType@@SAHK@Z; CType::IsStringType(ulong)
0x18004f526  test    eax, eax
0x18004f528  jz      loc_18004F6A1
0x18004f52e  mov     rcx, r14
0x18004f531  call    cs:__imp_??BCVar@@QEAAPEAGXZ; CVar::operator ushort *(void)
0x18004f537  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004f53b  inc     rcx
0x18004f53e  cmp     [rax+rcx*2], r15w
0x18004f543  jnz     short loc_18004F53B
0x18004f545  lea     esi, ds:2[rcx*2]
0x18004f54c  mov     [rbx], esi
0x18004f54e  cmp     edi, esi
0x18004f550  jnb     short loc_18004F564
0x18004f552  mov     eax, 8004103Ch
0x18004f557  add     rsp, 38h
0x18004f55b  pop     r15
0x18004f55d  pop     r14
0x18004f55f  pop     rdi
0x18004f560  pop     rsi
0x18004f561  pop     rbp
0x18004f562  pop     rbx
0x18004f563  retn
0x18004f564  mov     rbx, [rsp+68h+arg_20]
0x18004f56c  test    rbx, rbx
0x18004f56f  jz      short loc_18004F552
0x18004f571  mov     rcx, r14
0x18004f574  call    cs:__imp_??BCVar@@QEAAPEAGXZ; CVar::operator ushort *(void)
0x18004f57a  mov     edx, esi; unsigned __int64
0x18004f57c  mov     rcx, rbx; unsigned __int16 *
0x18004f57f  mov     r8, rax; unsigned __int16 *
0x18004f582  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f587  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f58e  lea     rax, WPP_GLOBAL_Control
0x18004f595  cmp     rcx, rax
0x18004f598  jz      short loc_18004F5A4
0x18004f59a  test    byte ptr [rcx+1Ch], 1
0x18004f59e  jnz     loc_18004F67A
0x18004f5a4  mov     eax, ebp
0x18004f5a6  jmp     short loc_18004F557
0x18004f5a8  cmp     esi, 14h
0x18004f5ab  jz      short loc_18004F5FC
0x18004f5ad  cmp     esi, 15h
0x18004f5b0  jnz     loc_18004F63A
0x18004f5b6  mov     dword ptr [rbx], 8
0x18004f5bc  cmp     edi, 8
0x18004f5bf  jb      short loc_18004F552
0x18004f5c1  mov     rbx, [rsp+68h+arg_20]
0x18004f5c9  test    rbx, rbx
0x18004f5cc  jz      short loc_18004F552
0x18004f5ce  mov     rcx, r14
0x18004f5d1  mov     [rsp+68h+var_48], r15
0x18004f5d6  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x18004f5dc  mov     rcx, rax
0x18004f5df  lea     rdx, [rsp+68h+var_48]
0x18004f5e4  call    cs:__imp_?ReadUI64@@YAHPEBGAEFA_K@Z; ReadUI64(ushort const *,unsigned __int64 &)
0x18004f5ea  test    eax, eax
0x18004f5ec  jz      loc_18004F6CF
0x18004f5f2  mov     rax, [rsp+68h+var_48]
0x18004f5f7  mov     [rbx], rax
0x18004f5fa  jmp     short loc_18004F587
0x18004f5fc  mov     dword ptr [rbx], 8
0x18004f602  cmp     edi, 8
0x18004f605  jb      loc_18004F552
0x18004f60b  mov     rbx, [rsp+68h+arg_20]
0x18004f613  test    rbx, rbx
0x18004f616  jz      loc_18004F552
0x18004f61c  mov     rcx, r14
0x18004f61f  mov     [rsp+68h+var_48], r15
0x18004f624  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x18004f62a  mov     rcx, rax
0x18004f62d  lea     rdx, [rsp+68h+var_48]
0x18004f632  call    cs:__imp_?ReadI64@@YAHPEBGAEFA_J@Z; ReadI64(ushort const *,__int64 &)
0x18004f638  jmp     short loc_18004F5EA
0x18004f63a  mov     ecx, esi; unsigned int
0x18004f63c  call    ?GetLength@CType@@SAKK@Z; CType::GetLength(ulong)
0x18004f641  mov     [rbx], eax
0x18004f643  cmp     edi, eax
0x18004f645  jb      loc_18004F552
0x18004f64b  mov     rdi, [rsp+68h+arg_20]
0x18004f653  test    rdi, rdi
0x18004f656  jz      loc_18004F552
0x18004f65c  mov     rcx, r14
0x18004f65f  mov     ebx, eax
0x18004f661  call    cs:__imp_?GetRawData@CVar@@QEAAPEAXXZ; CVar::GetRawData(void)
0x18004f667  mov     r8d, ebx; Size
0x18004f66a  mov     rcx, rdi; void *
0x18004f66d  mov     rdx, rax; Src
0x18004f670  call    memcpy_0
0x18004f675  jmp     loc_18004F587
0x18004f67a  cmp     byte ptr [rcx+19h], 2
0x18004f67e  jb      loc_18004F5A4
0x18004f684  mov     rcx, [rcx+10h]
0x18004f688  lea     r8, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids
0x18004f68f  mov     edx, 12h
0x18004f694  mov     r9d, ebp
0x18004f697  call    WPP_SF_d
0x18004f69c  jmp     loc_18004F5A4
0x18004f6a1  mov     dword ptr [rbx], 8
0x18004f6a7  cmp     edi, 8
0x18004f6aa  jb      loc_18004F552
0x18004f6b0  mov     rbx, [rsp+68h+arg_20]
0x18004f6b8  test    rbx, rbx
0x18004f6bb  jz      loc_18004F552
0x18004f6c1  mov     rcx, r14
0x18004f6c4  call    cs:__imp_?GetUnknown@CVar@@QEAAPEAUIUnknown@@XZ; CVar::GetUnknown(void)
0x18004f6ca  jmp     loc_18004F5F7
0x18004f6cf  mov     ebp, 8004101Eh
0x18004f6d4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004f6da  mov     rcx, rax
0x18004f6dd  mov     edx, ebp
0x18004f6df  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004f6e5  jmp     loc_18004F587
```
