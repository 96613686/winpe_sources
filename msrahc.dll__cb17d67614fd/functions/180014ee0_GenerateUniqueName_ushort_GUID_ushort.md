# GenerateUniqueName(ushort *,_GUID *,ushort * *)

- ea: `0x180014ee0`
- end: `0x180015054`
- name: `?GenerateUniqueName@@YAJPEAGPEAU_GUID@@PEAPEAG@Z`
- size: `372`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011c10`

## callees

- `0x180006b48`
- `0x18000f2d4`
- `0x180014660`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180014f46`
- `KERNEL32!GetProcessHeap` at `0x180015023`
- `KERNEL32!GetProcessHeap` at `0x180014f46`
- `KERNEL32!GetProcessHeap` at `0x180015023`
- `KERNEL32!HeapAlloc` at `0x180014f57`
- `KERNEL32!HeapAlloc` at `0x180014f57`
- `KERNEL32!HeapFree` at `0x180015031`
- `KERNEL32!HeapFree` at `0x180015031`

## string_xrefs

- `0x180014f80`: `base\diagnosis\ra\racommon\src\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall GenerateUniqueName(unsigned __int16 *a1, struct _GUID *a2, unsigned __int16 **a3)
{
  signed int v6; // eax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  int v9; // ebx
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  void *v15; // rdi
  HANDLE v16; // rax
  unsigned __int64 v18; // [rsp+E0h] [rbp+18h] BYREF

  *a3 = 0;
  v18 = 0;
  v6 = StringCchLengthW(a1, 0x7FFFFFFFu, &v18);
  v9 = v6;
  if ( v6 >= 0 )
  {
    v18 += 38LL;
    v10 = 2 * v18;
    ProcessHeap = GetProcessHeap();
    v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v10);
    *a3 = v12;
    if ( v12 )
    {
      v9 = StringCchPrintfW(
             v12,
             v18,
             L"%s-%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
             a1,
             a2->Data1,
             a2->Data2,
             a2->Data3,
             a2->Data4[0],
             a2->Data4[1],
             a2->Data4[2],
             a2->Data4[3],
             a2->Data4[4],
             a2->Data4[5],
             a2->Data4[6],
             a2->Data4[7]);
      if ( v9 >= 0 )
        return (unsigned int)v9;
    }
    else
    {
      v9 = -2147024882;
      CEventLogger::LogError(
        v14,
        v13,
        L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
        0x35u,
        L"GenerateUniqueName",
        0x8007000E);
    }
  }
  else
  {
    CEventLogger::LogError(
      v8,
      v7,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      0x2Cu,
      L"GenerateUniqueName",
      v6);
  }
  v15 = *a3;
  if ( *a3 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
    *a3 = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180014ee0  mov     rax, rsp
0x180014ee3  push    rbx
0x180014ee4  push    rbp
0x180014ee5  push    rsi
0x180014ee6  push    rdi
0x180014ee7  push    r12
0x180014ee9  push    r13
0x180014eeb  push    r14
0x180014eed  push    r15
0x180014eef  sub     rsp, 88h
0x180014ef6  mov     r15, rdx
0x180014ef9  mov     qword ptr [r8], 0
0x180014f00  mov     r14, r8
0x180014f03  mov     qword ptr [rax+18h], 0
0x180014f0b  lea     r8, [rax+18h]; unsigned __int64 *
0x180014f0f  mov     edx, 7FFFFFFFh; unsigned __int64
0x180014f14  mov     r13, rcx
0x180014f17  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180014f1c  mov     ebx, eax
0x180014f1e  test    eax, eax
0x180014f20  jns     short loc_180014F2E
0x180014f22  mov     [rsp+0C8h+var_A0], eax
0x180014f26  mov     r9d, 2Ch ; ','
0x180014f2c  jmp     short loc_180014F79
0x180014f2e  mov     rax, [rsp+0C8h+arg_10]
0x180014f36  add     rax, 26h ; '&'
0x180014f3a  mov     [rsp+0C8h+arg_10], rax
0x180014f42  lea     rbx, [rax+rax]
0x180014f46  call    cs:__imp_GetProcessHeap
0x180014f4c  mov     r8, rbx; dwBytes
0x180014f4f  mov     edx, 8; dwFlags
0x180014f54  mov     rcx, rax; hHeap
0x180014f57  call    cs:__imp_HeapAlloc
0x180014f5d  mov     [r14], rax
0x180014f60  mov     r12, rax
0x180014f63  test    rax, rax
0x180014f66  jnz     short loc_180014F96
0x180014f68  mov     ebx, 8007000Eh
0x180014f6d  mov     [rsp+0C8h+var_A0], 8007000Eh; unsigned int
0x180014f75  lea     r9d, [rax+35h]; unsigned int
0x180014f79  lea     rax, aGenerateunique; "GenerateUniqueName"
0x180014f80  lea     r8, aBaseDiagnosisR_9; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x180014f87  mov     [rsp+0C8h+var_A8], rax; unsigned __int16 *
0x180014f8c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180014f91  jmp     loc_18001501B
0x180014f96  movzx   eax, byte ptr [r15+0Fh]
0x180014f9b  movzx   ecx, byte ptr [r15+0Eh]
0x180014fa0  movzx   r8d, byte ptr [r15+0Dh]
0x180014fa5  movzx   r9d, byte ptr [r15+0Ch]
0x180014faa  movzx   r10d, byte ptr [r15+0Bh]
0x180014faf  movzx   r11d, byte ptr [r15+0Ah]
0x180014fb4  movzx   ebx, byte ptr [r15+9]
0x180014fb9  movzx   edi, byte ptr [r15+8]
0x180014fbe  movzx   esi, word ptr [r15+6]
0x180014fc3  movzx   ebp, word ptr [r15+4]
0x180014fc8  mov     rdx, [rsp+0C8h+arg_10]; unsigned __int64
0x180014fd0  mov     [rsp+0C8h+var_58], eax
0x180014fd4  mov     eax, [r15]
0x180014fd7  mov     [rsp+0C8h+var_60], ecx
0x180014fdb  mov     rcx, r12; unsigned __int16 *
0x180014fde  mov     [rsp+0C8h+var_68], r8d
0x180014fe3  lea     r8, aS08x04x04x02x0; "%s-%08x-%04x-%04x-%02x%02x-%02x%02x%02x"...
0x180014fea  mov     [rsp+0C8h+var_70], r9d
0x180014fef  mov     r9, r13
0x180014ff2  mov     [rsp+0C8h+var_78], r10d
0x180014ff7  mov     [rsp+0C8h+var_80], r11d
0x180014ffc  mov     [rsp+0C8h+var_88], ebx
0x180015000  mov     [rsp+0C8h+var_90], edi
0x180015004  mov     [rsp+0C8h+var_98], esi
0x180015008  mov     [rsp+0C8h+var_A0], ebp
0x18001500c  mov     dword ptr [rsp+0C8h+var_A8], eax
0x180015010  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015015  mov     ebx, eax
0x180015017  test    eax, eax
0x180015019  jns     short loc_18001503E
0x18001501b  mov     rdi, [r14]
0x18001501e  test    rdi, rdi
0x180015021  jz      short loc_18001503E
0x180015023  call    cs:__imp_GetProcessHeap
0x180015029  mov     r8, rdi; lpMem
0x18001502c  xor     edx, edx; dwFlags
0x18001502e  mov     rcx, rax; hHeap
0x180015031  call    cs:__imp_HeapFree
0x180015037  mov     qword ptr [r14], 0
0x18001503e  mov     eax, ebx
0x180015040  add     rsp, 88h
0x180015047  pop     r15
0x180015049  pop     r14
0x18001504b  pop     r13
0x18001504d  pop     r12
0x18001504f  pop     rdi
0x180015050  pop     rsi
0x180015051  pop     rbp
0x180015052  pop     rbx
0x180015053  retn
```
