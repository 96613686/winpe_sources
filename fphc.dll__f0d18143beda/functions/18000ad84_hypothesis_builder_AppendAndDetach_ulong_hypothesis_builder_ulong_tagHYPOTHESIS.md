# _hypothesis_builder::AppendAndDetach(ulong,_hypothesis_builder *,ulong *,tagHYPOTHESIS * *)

- ea: `0x18000ad84`
- end: `0x18000af16`
- name: `?AppendAndDetach@_hypothesis_builder@@QEAAJKPEAV1@PEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `402`
- prototype: `__int64 __usercall@<rax>(_hypothesis_builder *__hidden this@<rcx>, unsigned int@<edx>, struct _hypothesis_builder *@<r8>, unsigned int *@<r9>, struct tagHYPOTHESIS **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006970`

## callees

- `0x18000ad84`
- `0x18000af1c`
- `0x18000afc8`
- `0x18000edb8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000adea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aeca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000adea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aeca`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::AppendAndDetach(
        _hypothesis_builder *this,
        unsigned int a2,
        struct _hypothesis_builder *a3,
        unsigned int *a4,
        struct tagHYPOTHESIS **a5)
{
  struct tagHYPOTHESIS **v5; // r12
  unsigned int v6; // r14d
  __int64 result; // rax
  SIZE_T v12; // rsi
  struct tagHYPOTHESIS *v13; // rax
  struct tagHYPOTHESIS *v14; // rdi
  int v15; // ebx
  unsigned int v16; // esi
  struct tagHYPOTHESIS *v17; // rbx
  __int64 v18; // rdi
  _BYTE *v19; // rax
  unsigned int v20[22]; // [rsp+20h] [rbp-58h] BYREF

  v5 = a5;
  v6 = 0;
  if ( !a5 || !a4 )
    return 2147942487LL;
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a2 > 0x7FFFFFE )
        return 2147942934LL;
      v12 = 32LL * (a2 + 1);
      v13 = (struct tagHYPOTHESIS *)CoTaskMemAlloc(v12);
      v14 = v13;
      if ( !v13 )
        return 2147942414LL;
      for ( ; v12; --v12 )
      {
        LOBYTE(v13->pwszClassName) = 0;
        v13 = (struct tagHYPOTHESIS *)((char *)v13 + 1);
      }
      v20[0] = 0;
      LODWORD(a5) = 0;
      v15 = _hypothesis_builder::DetachInPlace(this, v14, (unsigned int *)&a5, v20);
      if ( v15 >= 0 )
      {
        v16 = (unsigned int)a5;
        v17 = (struct tagHYPOTHESIS *)((char *)v14 + v20[0]);
        if ( a2 )
        {
          do
          {
            if ( (int)_hypothesis_builder::DetachInPlace(
                        (struct _hypothesis_builder *)((char *)a3 + 40 * v6),
                        v17,
                        (unsigned int *)&a5,
                        v20) < 0 )
              break;
            ++v6;
            v16 += (unsigned int)a5;
            v17 = (struct tagHYPOTHESIS *)((char *)v17 + v20[0]);
          }
          while ( v6 < a2 );
        }
        *v5 = v14;
        result = 0;
        *a4 = v16;
      }
      else
      {
        CoTaskMemFree(v14);
        return (unsigned int)v15;
      }
      return result;
    }
    return 2147942487LL;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 4) || *((_QWORD *)this + 3) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v18 = 32;
    v19 = CoTaskMemAlloc(0x20u);
    *((_QWORD *)this + 4) = v19;
    if ( !v19 )
      return 2147942414LL;
    do
    {
      *v19++ = 0;
      --v18;
    }
    while ( v18 );
  }
  _hypothesis_builder::DoDetach(this, v5);
  result = 0;
  *a4 = 1;
  return result;
}

```

## disassembly

```asm
0x18000ad84  push    rbx
0x18000ad86  push    rbp
0x18000ad87  push    rsi
0x18000ad88  push    rdi
0x18000ad89  push    r12
0x18000ad8b  push    r13
0x18000ad8d  push    r14
0x18000ad8f  push    r15
0x18000ad91  sub     rsp, 38h
0x18000ad95  mov     r12, [rsp+78h+arg_20]
0x18000ad9d  xor     r14d, r14d
0x18000ada0  mov     r15, r9
0x18000ada3  mov     r13, r8
0x18000ada6  mov     ebp, edx
0x18000ada8  mov     rbx, rcx
0x18000adab  test    r12, r12
0x18000adae  jz      loc_18000AF00
0x18000adb4  test    r9, r9
0x18000adb7  jz      loc_18000AF00
0x18000adbd  test    edx, edx
0x18000adbf  jz      loc_18000AEAC
0x18000adc5  test    r8, r8
0x18000adc8  jz      loc_18000AF00
0x18000adce  cmp     edx, 7FFFFFEh
0x18000add4  jbe     short loc_18000ADE0
0x18000add6  mov     eax, 80070216h
0x18000addb  jmp     loc_18000AF05
0x18000ade0  lea     esi, [rdx+1]
0x18000ade3  shl     rsi, 5
0x18000ade7  mov     rcx, rsi; cb
0x18000adea  call    cs:__imp_CoTaskMemAlloc
0x18000adf0  mov     rdi, rax
0x18000adf3  test    rax, rax
0x18000adf6  jnz     short loc_18000AE02
0x18000adf8  mov     eax, 8007000Eh
0x18000adfd  jmp     loc_18000AF05
0x18000ae02  test    rsi, rsi
0x18000ae05  jz      short loc_18000AE13
0x18000ae07  mov     [rax], r14b
0x18000ae0a  inc     rax
0x18000ae0d  sub     rsi, 1
0x18000ae11  jnz     short loc_18000AE07
0x18000ae13  lea     r9, [rsp+78h+var_58]; unsigned int *
0x18000ae18  mov     [rsp+78h+var_58], r14d
0x18000ae1d  lea     r8, [rsp+78h+arg_20]; unsigned int *
0x18000ae25  mov     dword ptr [rsp+78h+arg_20], r14d
0x18000ae2d  mov     rdx, rdi; struct tagHYPOTHESIS *
0x18000ae30  mov     rcx, rbx; this
0x18000ae33  call    ?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z; _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)
0x18000ae38  mov     ebx, eax
0x18000ae3a  test    eax, eax
0x18000ae3c  jns     short loc_18000AE4E
0x18000ae3e  mov     rcx, rdi; pv
0x18000ae41  call    cs:__imp_CoTaskMemFree
0x18000ae47  mov     eax, ebx
0x18000ae49  jmp     loc_18000AF05
0x18000ae4e  mov     ebx, [rsp+78h+var_58]
0x18000ae52  mov     esi, dword ptr [rsp+78h+arg_20]
0x18000ae59  add     rbx, rdi
0x18000ae5c  test    ebp, ebp
0x18000ae5e  jz      short loc_18000AEA1
0x18000ae60  mov     eax, r14d
0x18000ae63  lea     r9, [rsp+78h+var_58]; unsigned int *
0x18000ae68  lea     r8, [rsp+78h+arg_20]; unsigned int *
0x18000ae70  mov     rdx, rbx; struct tagHYPOTHESIS *
0x18000ae73  lea     rcx, [rax+rax*4]
0x18000ae77  lea     rcx, ds:0[rcx*8]
0x18000ae7f  add     rcx, r13; this
0x18000ae82  call    ?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z; _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)
0x18000ae87  test    eax, eax
0x18000ae89  js      short loc_18000AEA1
0x18000ae8b  mov     eax, [rsp+78h+var_58]
0x18000ae8f  inc     r14d
0x18000ae92  add     esi, dword ptr [rsp+78h+arg_20]
0x18000ae99  add     rbx, rax
0x18000ae9c  cmp     r14d, ebp
0x18000ae9f  jb      short loc_18000AE60
0x18000aea1  mov     [r12], rdi
0x18000aea5  xor     eax, eax
0x18000aea7  mov     [r15], esi
0x18000aeaa  jmp     short loc_18000AF05
0x18000aeac  cmp     [rcx+20h], r14
0x18000aeb0  jnz     short loc_18000AEE9
0x18000aeb2  cmp     [rcx+10h], r14d
0x18000aeb6  jnz     short loc_18000AEBE
0x18000aeb8  cmp     [rcx+18h], r14
0x18000aebc  jz      short loc_18000AEC3
0x18000aebe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000aec3  mov     edi, 20h ; ' '
0x18000aec8  mov     ecx, edi; cb
0x18000aeca  call    cs:__imp_CoTaskMemAlloc
0x18000aed0  mov     [rbx+20h], rax
0x18000aed4  test    rax, rax
0x18000aed7  jz      loc_18000ADF8
0x18000aedd  mov     [rax], r14b
0x18000aee0  inc     rax
0x18000aee3  sub     rdi, 1
0x18000aee7  jnz     short loc_18000AEDD
0x18000aee9  mov     rdx, r12; struct tagHYPOTHESIS **
0x18000aeec  mov     rcx, rbx; this
0x18000aeef  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x18000aef4  mov     eax, r14d
0x18000aef7  mov     dword ptr [r15], 1
0x18000aefe  jmp     short loc_18000AF05
0x18000af00  mov     eax, 80070057h
0x18000af05  add     rsp, 38h
0x18000af09  pop     r15
0x18000af0b  pop     r14
0x18000af0d  pop     r13
0x18000af0f  pop     r12
0x18000af11  pop     rdi
0x18000af12  pop     rsi
0x18000af13  pop     rbp
0x18000af14  pop     rbx
0x18000af15  retn
```
