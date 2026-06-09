# TMBSchemaCompilation::SetBinFileVersion(long)

- ea: `0x180017814`
- end: `0x18001795e`
- name: `?SetBinFileVersion@TMBSchemaCompilation@@AEAAJJ@Z`
- size: `330`
- prototype: `__int64 __fastcall(TMBSchemaCompilation *this, __int32)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180015f34`
- `0x180017b70`

## callees

- `0x180005870`
- `0x1800113fc`
- `0x180016a18`
- `0x180017614`
- `0x180017814`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18001788c`
- `msvcrt!swprintf_s` at `0x18001788c`
- `KERNEL32!DeleteFileW` at `0x180017928`
- `KERNEL32!DeleteFileW` at `0x180017928`
- `ole32!CoTaskMemAlloc` at `0x180017853`
- `ole32!CoTaskMemAlloc` at `0x180017853`

## pseudocode

```c
__int64 __fastcall TMBSchemaCompilation::SetBinFileVersion(TMBSchemaCompilation *this, __int32 a2)
{
  wchar_t *v5; // rax
  const WCHAR *v6; // rbx
  int v7; // edi
  bool v8; // r8
  char *v9; // r14
  int v10; // eax
  int v11; // ebx
  wchar_t *v12; // [rsp+60h] [rbp+18h] BYREF

  if ( a2 < 0 )
    return 2147942487LL;
  v5 = (wchar_t *)CoTaskMemAlloc(saturated_mul(*((_QWORD *)this + 320), 2u));
  v6 = v5;
  v12 = v5;
  if ( v5 )
  {
    swprintf_s(v5, *((_QWORD *)this + 320), L"%sMBSchema.bin.%08xh", *((_QWORD *)this + 321), a2);
    v9 = (char *)this + 40 * (a2 % 0x3Fu);
    v10 = *((_DWORD *)v9 + 8);
    if ( v10 )
    {
      *((_DWORD *)v9 + 8) = v10 + 1;
      v7 = 0;
    }
    else
    {
      *((_DWORD *)v9 + 8) = 1;
      *((_DWORD *)v9 + 9) = a2;
      v7 = TFileMapping::Load((TMBSchemaCompilation *)((char *)this + 40 * (a2 % 0x3Fu)), v6, v8);
      if ( v7 < 0 )
      {
        DeleteFileW(v6);
        goto LABEL_15;
      }
    }
    if ( *((_DWORD *)v9 + 6) > 0x1000u && FixedTableHeap::IsValid(*((FixedTableHeap **)v9 + 2)) )
    {
      v11 = *((_DWORD *)this + 644);
      _InterlockedExchange((volatile __int32 *)this + 644, a2);
      if ( v11 >= 0 )
      {
        TMBSchemaCompilation::DeleteBinFileVersion(this, v11);
        if ( v11 > 0 )
          TMBSchemaCompilation::DeleteBinFileVersion(this, v11 - 1);
      }
    }
    else
    {
      TMBSchemaCompilation::DeleteBinFileVersion(this, a2);
      v7 = -2145318814;
    }
    goto LABEL_15;
  }
  v7 = -2147024882;
LABEL_15:
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180017814  mov     [rsp+arg_0], rbx
0x180017819  mov     [rsp+arg_8], rbp
0x18001781e  push    rsi
0x18001781f  push    rdi
0x180017820  push    r14
0x180017822  sub     rsp, 30h
0x180017826  mov     ebp, edx
0x180017828  mov     rsi, rcx
0x18001782b  test    edx, edx
0x18001782d  jns     short loc_180017839
0x18001782f  mov     eax, 80070057h
0x180017834  jmp     loc_18001794B
0x180017839  mov     eax, 2
0x18001783e  mul     qword ptr [rcx+0A00h]
0x180017845  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001784c  cmovb   rax, rcx
0x180017850  mov     rcx, rax; cb
0x180017853  call    cs:__imp_CoTaskMemAlloc
0x180017859  mov     rbx, rax
0x18001785c  mov     [rsp+48h+arg_10], rax
0x180017861  test    rax, rax
0x180017864  jnz     short loc_180017870
0x180017866  mov     edi, 8007000Eh
0x18001786b  jmp     loc_18001793F
0x180017870  mov     [rsp+48h+var_28], ebp
0x180017874  mov     r9, [rsi+0A08h]
0x18001787b  lea     r8, aSmbschemaBin08; "%sMBSchema.bin.%08xh"
0x180017882  mov     rdx, [rsi+0A00h]; BufferCount
0x180017889  mov     rcx, rbx; Buffer
0x18001788c  call    cs:__imp_swprintf_s
0x180017892  mov     eax, 4104105h
0x180017897  mul     ebp
0x180017899  mov     eax, ebp
0x18001789b  sub     eax, edx
0x18001789d  shr     eax, 1
0x18001789f  add     eax, edx
0x1800178a1  shr     eax, 5
0x1800178a4  imul    eax, 3Fh ; '?'
0x1800178a7  mov     ecx, ebp
0x1800178a9  sub     ecx, eax
0x1800178ab  movsxd  rax, ecx
0x1800178ae  lea     rcx, [rax+rax*4]
0x1800178b2  lea     r14, [rsi+rcx*8]
0x1800178b6  mov     eax, [r14+20h]
0x1800178ba  test    eax, eax
0x1800178bc  jz      short loc_180017908
0x1800178be  inc     eax
0x1800178c0  mov     [r14+20h], eax
0x1800178c4  xor     edi, edi
0x1800178c6  cmp     dword ptr [r14+18h], 1000h
0x1800178ce  jbe     short loc_180017930
0x1800178d0  mov     rcx, [r14+10h]; this
0x1800178d4  call    ?IsValid@FixedTableHeap@@QEBA_NXZ; FixedTableHeap::IsValid(void)
0x1800178d9  test    al, al
0x1800178db  jz      short loc_180017930
0x1800178dd  mov     ebx, [rsi+0A10h]
0x1800178e3  xchg    ebp, [rsi+0A10h]
0x1800178e9  test    ebx, ebx
0x1800178eb  js      short loc_18001793F
0x1800178ed  mov     edx, ebx; int
0x1800178ef  mov     rcx, rsi; this
0x1800178f2  call    ?DeleteBinFileVersion@TMBSchemaCompilation@@AEAAJJ@Z; TMBSchemaCompilation::DeleteBinFileVersion(long)
0x1800178f7  test    ebx, ebx
0x1800178f9  jle     short loc_18001793F
0x1800178fb  lea     edx, [rbx-1]; int
0x1800178fe  mov     rcx, rsi; this
0x180017901  call    ?DeleteBinFileVersion@TMBSchemaCompilation@@AEAAJJ@Z; TMBSchemaCompilation::DeleteBinFileVersion(long)
0x180017906  jmp     short loc_18001793F
0x180017908  mov     dword ptr [r14+20h], 1
0x180017910  mov     [r14+24h], ebp
0x180017914  mov     rdx, rbx; lpFileName
0x180017917  mov     rcx, r14; this
0x18001791a  call    ?Load@TFileMapping@@QEAAJPEBG_N@Z; TFileMapping::Load(ushort const *,bool)
0x18001791f  mov     edi, eax
0x180017921  test    eax, eax
0x180017923  jns     short loc_1800178C6
0x180017925  mov     rcx, rbx; lpFileName
0x180017928  call    cs:__imp_DeleteFileW
0x18001792e  jmp     short loc_18001793F
0x180017930  mov     edx, ebp; int
0x180017932  mov     rcx, rsi; this
0x180017935  call    ?DeleteBinFileVersion@TMBSchemaCompilation@@AEAAJJ@Z; TMBSchemaCompilation::DeleteBinFileVersion(long)
0x18001793a  mov     edi, 80210862h
0x18001793f  lea     rcx, [rsp+48h+arg_10]; void *
0x180017944  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x180017949  mov     eax, edi
0x18001794b  mov     rbx, [rsp+48h+arg_0]
0x180017950  mov     rbp, [rsp+48h+arg_8]
0x180017955  add     rsp, 30h
0x180017959  pop     r14
0x18001795b  pop     rdi
0x18001795c  pop     rsi
0x18001795d  retn
```
