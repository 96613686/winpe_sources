# CTSimpleArray<MaxPathString,4294967294,CTPolicyCoTaskMem<MaxPathString>,CSimpleArrayStandardCompareHelper<MaxPathString>,CSimpleArrayStandardMergeHelper<MaxPathString>>::_EnsureCapacity(unsigned __int64,unsigned __int64)

- ea: `0x18001e7c8`
- end: `0x18001e8be`
- name: `?_EnsureCapacity@?$CTSimpleArray@VMaxPathString@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@VMaxPathString@@@@V?$CSimpleArrayStandardCompareHelper@VMaxPathString@@@@V?$CSimpleArrayStandardMergeHelper@VMaxPathString@@@@@@QEAAJ_K0@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001cba4`

## callees

- `0x18001d994`
- `0x18001da6c`
- `0x18001e7c8`
- `0x18003104a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001e874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001e874`

## pseudocode

```c
__int64 __fastcall CTSimpleArray<MaxPathString,4294967294,CTPolicyCoTaskMem<MaxPathString>,CSimpleArrayStandardCompareHelper<MaxPathString>,CSimpleArrayStandardMergeHelper<MaxPathString>>::_EnsureCapacity(
        _QWORD *a1,
        unsigned __int64 a2,
        SIZE_T a3)
{
  unsigned __int64 v3; // rbx
  __int64 result; // rax
  unsigned __int64 v6; // r10
  SIZE_T v7; // r9
  __int64 v8; // r10
  SIZE_T v9; // rcx
  void *v10; // r9
  SIZE_T v11; // r14
  char *v12; // rax
  char *v13; // rdi
  unsigned __int64 v14; // rax
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF

  cb = a3;
  v3 = 4294967294LL;
  result = 2147942522LL;
  if ( a2 <= 0xFFFFFFFE )
  {
    v6 = a1[3];
    result = 0;
    if ( a2 > v6 )
    {
      cb = 0;
      result = ULongLongMult(v6, 2u, &cb);
      if ( (int)result >= 0 )
      {
        v9 = cb;
        if ( cb - v8 > 0x1000 )
          v9 = v8 + 4096;
        if ( v7 > v9 || v9 <= 0xFFFFFFFE )
        {
          v3 = v9;
          if ( v7 > v9 )
            v3 = v7;
        }
        cb = 0;
        result = ULongLongMult(v3, 0x208u, &cb);
        if ( (int)result >= 0 )
        {
          v11 = cb;
          v12 = (char *)CoTaskMemRealloc(v10, cb);
          v13 = v12;
          if ( v12 )
          {
            v14 = CTCoAllocPolicy::_CoTaskMemSize(v12);
            if ( v14 > v11 )
              memset_0(&v13[v11], 0, v14 - v11);
            result = 0;
          }
          else
          {
            result = 2147942414LL;
          }
          if ( (int)result >= 0 )
          {
            a1[3] = v3;
            *a1 = v13;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e7c8  mov     [rsp+cb], r8
0x18001e7cd  push    rbx
0x18001e7ce  push    rsi
0x18001e7cf  push    rdi
0x18001e7d0  push    r14
0x18001e7d2  sub     rsp, 28h
0x18001e7d6  mov     ebx, 0FFFFFFFEh
0x18001e7db  mov     r9, rdx
0x18001e7de  mov     rsi, rcx
0x18001e7e1  mov     eax, 8007007Ah
0x18001e7e6  cmp     rdx, rbx
0x18001e7e9  ja      loc_18001E8B4
0x18001e7ef  mov     r10, [rcx+18h]
0x18001e7f3  xor     eax, eax
0x18001e7f5  cmp     rdx, r10
0x18001e7f8  jbe     loc_18001E8B4
0x18001e7fe  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18001e803  mov     [rsp+48h+cb], rax
0x18001e808  lea     edx, [rax+2]; unsigned __int64
0x18001e80b  mov     rcx, r10; unsigned __int64
0x18001e80e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001e813  test    eax, eax
0x18001e815  js      loc_18001E8B4
0x18001e81b  mov     rcx, [rsp+48h+cb]
0x18001e820  mov     rax, rcx
0x18001e823  sub     rax, r10
0x18001e826  cmp     rax, 1000h
0x18001e82c  jbe     short loc_18001E835
0x18001e82e  lea     rcx, [r10+1000h]
0x18001e835  cmp     r9, rcx
0x18001e838  ja      short loc_18001E83F
0x18001e83a  cmp     rcx, rbx
0x18001e83d  ja      short loc_18001E849
0x18001e83f  cmp     r9, rcx
0x18001e842  mov     rbx, rcx
0x18001e845  cmova   rbx, r9
0x18001e849  mov     r9, [rsi]
0x18001e84c  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18001e851  xor     edi, edi
0x18001e853  mov     edx, 208h; unsigned __int64
0x18001e858  mov     rcx, rbx; unsigned __int64
0x18001e85b  mov     [rsp+48h+cb], rdi
0x18001e860  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001e865  test    eax, eax
0x18001e867  js      short loc_18001E8B4
0x18001e869  mov     r14, [rsp+48h+cb]
0x18001e86e  mov     rcx, r9; pv
0x18001e871  mov     rdx, r14; cb
0x18001e874  call    cs:__imp_CoTaskMemRealloc
0x18001e87a  mov     rdi, rax
0x18001e87d  test    rax, rax
0x18001e880  jz      short loc_18001E8A4
0x18001e882  mov     rcx, rax; void *
0x18001e885  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001e88a  cmp     rax, r14
0x18001e88d  jbe     short loc_18001E8A0
0x18001e88f  sub     rax, r14
0x18001e892  lea     rcx, [r14+rdi]; void *
0x18001e896  mov     r8, rax; Size
0x18001e899  xor     edx, edx; Val
0x18001e89b  call    memset_0
0x18001e8a0  xor     eax, eax
0x18001e8a2  jmp     short loc_18001E8A9
0x18001e8a4  mov     eax, 8007000Eh
0x18001e8a9  test    eax, eax
0x18001e8ab  js      short loc_18001E8B4
0x18001e8ad  mov     [rsi+18h], rbx
0x18001e8b1  mov     [rsi], rdi
0x18001e8b4  add     rsp, 28h
0x18001e8b8  pop     r14
0x18001e8ba  pop     rdi
0x18001e8bb  pop     rsi
0x18001e8bc  pop     rbx
0x18001e8bd  retn
```
