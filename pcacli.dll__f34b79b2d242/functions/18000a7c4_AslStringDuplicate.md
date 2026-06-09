# AslStringDuplicate

- ea: `0x18000a7c4`
- end: `0x18000a9a5`
- name: `AslStringDuplicate`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180006c80`

## callees

- `0x180006880`
- `0x180007668`
- `0x180007738`
- `0x180008b18`
- `0x18000a7c4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000a8d7`
- `ntdll!RtlAllocateHeap` at `0x18000a8d7`

## string_xrefs

- `0x18000a929`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicate(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rdi
  int v5; // eax
  int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rdx
  SIZE_T v11; // rax
  unsigned __int16 *Heap; // rax
  unsigned __int64 v14; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h]

  v14 = 0;
  v4 = 0;
  *a1 = 0;
  if ( !a2 )
    goto LABEL_21;
  v5 = RtlStringCchLengthW(a2, a2, &v14);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = "RtlStringCchLengthW failed [%x]";
    v8 = 590;
LABEL_4:
    AslLogCallPrintf(1, "AslStringDuplicate", v8, v7, v5);
    goto LABEL_22;
  }
  v9 = v14 + 1;
  if ( v14 + 1 < v14 )
  {
    v9 = -1;
    v14 = -1;
    v6 = -1073741675;
    v10 = -1;
  }
  else
  {
    ++v14;
    v6 = 0;
    v10 = v9;
  }
  if ( v6 >= 0 )
  {
    v15 = 0;
    v11 = 2 * v10;
    if ( is_mul_ok(v10, 2u) )
    {
      v6 = 0;
    }
    else
    {
      v11 = -1;
      v6 = -1073741675;
    }
    if ( v6 < 0 )
    {
      AslLogCallPrintf(1, "AslStringDuplicate", 608, "SIZE_T arithmetic failed [%x]", v6);
      goto LABEL_22;
    }
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v11);
    v4 = Heap;
    if ( !Heap )
    {
      v6 = -1073741801;
      AslLogCallPrintf(1, "AslStringDuplicate", 615, "Out of memory");
      goto LABEL_22;
    }
    v5 = RtlStringCchCopyW(Heap, v9, a2);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = "RtlStringCchCopyW failed [%x]";
      v8 = 632;
      goto LABEL_4;
    }
    *a1 = v4;
    v4 = 0;
LABEL_21:
    v6 = 0;
    goto LABEL_22;
  }
  AslLogCallPrintf(1, "AslStringDuplicate", 602, "SIZE_T arithmetic failed [%x]", v6);
LABEL_22:
  AslFree(NtCurrentPeb()->ProcessHeap, v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a7c4  mov     rax, rsp
0x18000a7c7  mov     [rax+8], rbx
0x18000a7cb  mov     [rax+10h], rsi
0x18000a7cf  push    rdi
0x18000a7d0  push    r14
0x18000a7d2  push    r15
0x18000a7d4  sub     rsp, 40h
0x18000a7d8  mov     r14, rdx
0x18000a7db  mov     r15, rcx
0x18000a7de  mov     qword ptr [rax+18h], 0
0x18000a7e6  xor     edi, edi
0x18000a7e8  mov     [rax-20h], rdi
0x18000a7ec  mov     [rcx], rdi
0x18000a7ef  test    rdx, rdx
0x18000a7f2  jz      loc_18000A945
0x18000a7f8  lea     r8, [rax+18h]
0x18000a7fc  mov     rcx, rdx
0x18000a7ff  call    RtlStringCchLengthW
0x18000a804  mov     ebx, eax
0x18000a806  mov     [rsp+58h+var_28], eax
0x18000a80a  test    eax, eax
0x18000a80c  jns     short loc_18000A835
0x18000a80e  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x18000a815  mov     r8d, 24Eh
0x18000a81b  mov     [rsp+58h+var_38], eax
0x18000a81f  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x18000a826  mov     ecx, 1
0x18000a82b  call    AslLogCallPrintf
0x18000a830  jmp     loc_18000A94B
0x18000a835  mov     rax, [rsp+58h+arg_10]
0x18000a83a  lea     rsi, [rax+1]
0x18000a83e  cmp     rsi, rax
0x18000a841  jb      short loc_18000A853
0x18000a843  mov     [rsp+58h+arg_10], rsi
0x18000a848  xor     ebx, ebx
0x18000a84a  mov     rdx, rsi
0x18000a84d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a851  jmp     short loc_18000A867
0x18000a853  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a857  mov     rsi, rcx
0x18000a85a  mov     [rsp+58h+arg_10], rcx
0x18000a85f  mov     ebx, 0C0000095h
0x18000a864  mov     rdx, rcx
0x18000a867  mov     [rsp+58h+var_28], ebx
0x18000a86b  test    ebx, ebx
0x18000a86d  jns     short loc_18000A882
0x18000a86f  mov     [rsp+58h+var_38], ebx
0x18000a873  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x18000a87a  mov     r8d, 25Ah
0x18000a880  jmp     short loc_18000A81F
0x18000a882  mov     [rsp+58h+arg_18], 0
0x18000a88b  mov     eax, 2
0x18000a890  mul     rdx
0x18000a893  test    rdx, rdx
0x18000a896  jnz     short loc_18000A89C
0x18000a898  xor     ebx, ebx
0x18000a89a  jmp     short loc_18000A8A4
0x18000a89c  mov     rax, rcx
0x18000a89f  mov     ebx, 0C0000095h
0x18000a8a4  mov     [rsp+58h+var_28], ebx
0x18000a8a8  test    ebx, ebx
0x18000a8aa  jns     short loc_18000A8C2
0x18000a8ac  mov     [rsp+58h+var_38], ebx
0x18000a8b0  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x18000a8b7  mov     r8d, 260h
0x18000a8bd  jmp     loc_18000A81F
0x18000a8c2  mov     rcx, gs:60h
0x18000a8cb  mov     r8, rax; Size
0x18000a8ce  mov     edx, 8; Flags
0x18000a8d3  mov     rcx, [rcx+30h]; HeapHandle
0x18000a8d7  call    cs:__imp_RtlAllocateHeap
0x18000a8dd  mov     rdi, rax
0x18000a8e0  mov     [rsp+58h+var_20], rax
0x18000a8e5  test    rax, rax
0x18000a8e8  jnz     short loc_18000A911
0x18000a8ea  mov     ebx, 0C0000017h
0x18000a8ef  mov     [rsp+58h+var_28], ebx
0x18000a8f3  lea     r9, aOutOfMemory; "Out of memory"
0x18000a8fa  mov     r8d, 267h
0x18000a900  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x18000a907  lea     ecx, [rax+1]
0x18000a90a  call    AslLogCallPrintf
0x18000a90f  jmp     short loc_18000A94B
0x18000a911  mov     r8, r14; unsigned __int16 *
0x18000a914  mov     rdx, rsi; unsigned __int64
0x18000a917  mov     rcx, rdi; unsigned __int16 *
0x18000a91a  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a91f  mov     ebx, eax
0x18000a921  mov     [rsp+58h+var_28], eax
0x18000a925  test    eax, eax
0x18000a927  jns     short loc_18000A93B
0x18000a929  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18000a930  mov     r8d, 278h
0x18000a936  jmp     loc_18000A81B
0x18000a93b  mov     [r15], rdi
0x18000a93e  xor     edi, edi
0x18000a940  mov     [rsp+58h+var_20], rdi
0x18000a945  xor     ebx, ebx
0x18000a947  mov     [rsp+58h+var_28], ebx
0x18000a94b  jmp     short loc_18000A97A
0x18000a94d  mov     ebx, eax
0x18000a94f  mov     [rsp+58h+var_28], eax
0x18000a953  mov     [rsp+58h+var_38], eax
0x18000a957  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x18000a95e  mov     r8d, 289h
0x18000a964  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x18000a96b  mov     ecx, 1
0x18000a970  call    AslLogCallPrintf
0x18000a975  mov     rdi, [rsp+58h+var_20]
0x18000a97a  mov     rcx, gs:60h
0x18000a983  mov     rdx, rdi
0x18000a986  mov     rcx, [rcx+30h]
0x18000a98a  call    AslFree
0x18000a98f  mov     eax, ebx
0x18000a991  mov     rbx, [rsp+58h+arg_0]
0x18000a996  mov     rsi, [rsp+58h+arg_8]
0x18000a99b  add     rsp, 40h
0x18000a99f  pop     r15
0x18000a9a1  pop     r14
0x18000a9a3  pop     rdi
0x18000a9a4  retn
0x18000c4ea  push    rbp
0x18000c4ec  sub     rsp, 30h
0x18000c4f0  mov     rbp, rdx
0x18000c4f3  mov     rax, [rcx]
0x18000c4f6  xor     ecx, ecx
0x18000c4f8  cmp     dword ptr [rax], 0C00000FDh
0x18000c4fe  setnz   cl
0x18000c501  mov     [rbp+34h], ecx
0x18000c504  mov     eax, [rbp+34h]
0x18000c507  add     rsp, 30h
0x18000c50b  pop     rbp
0x18000c50c  retn
```
