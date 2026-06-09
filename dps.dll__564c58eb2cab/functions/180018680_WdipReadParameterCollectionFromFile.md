# WdipReadParameterCollectionFromFile

- ea: `0x180018680`
- end: `0x180018842`
- name: `WdipReadParameterCollectionFromFile`
- size: `450`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013214`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180008f70`
- `0x180009090`
- `0x180009660`
- `0x18000a856`
- `0x180017b20`
- `0x180018680`

## string_xrefs

- `0x1800186d4`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x1800187f7`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x1800186cd`: `WdipReadParameterCollectionFromFile`
- `0x1800187f0`: `WdipReadParameterCollectionFromFile`

## pseudocode

```c
__int64 __fastcall WdipReadParameterCollectionFromFile(__int64 a1, void *a2)
{
  int v4; // r8d
  unsigned int v5; // ebx
  int Args; // eax
  int v7; // eax
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  unsigned int v10; // r15d
  struct __WDIP_PARAMETER *ParameterFromFile; // rax
  unsigned int v12; // ecx
  unsigned int v14; // edx
  __int64 v15; // rax
  _QWORD *v16; // rcx
  unsigned int v17; // [rsp+68h] [rbp+38h] BYREF
  int v18; // [rsp+70h] [rbp+40h] BYREF
  int Buffer; // [rsp+78h] [rbp+48h] BYREF

  v18 = 0;
  v17 = 0;
  Buffer = 0;
  if ( !a2 )
  {
    v4 = 1028;
LABEL_3:
    v5 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterCollectionFromFile",
      v4,
      (int)L"Error = %d",
      87);
    return v5;
  }
  if ( !a1 )
  {
    v4 = 1029;
    goto LABEL_3;
  }
  Args = WdipReadFile(a2, (char *)&Buffer, 4u, &v18);
  v5 = Args;
  if ( Args >= 0 )
  {
    v7 = WdipReadFile(a2, (char *)&v17, 4u, &v18);
    v5 = v7;
    if ( v7 >= 0 )
    {
      v8 = WdipAlloc(8LL * v17);
      v9 = v8;
      if ( v8 )
      {
        memset_0(v8, 0, 8LL * v17);
        v10 = v17;
        v17 = 0;
        if ( v10 )
        {
          while ( 1 )
          {
            ParameterFromFile = WdipReadParameterFromFile(a2);
            v9[v17] = ParameterFromFile;
            v12 = v17;
            if ( !v9[v17] )
              break;
            ++v17;
            if ( v12 + 1 >= v10 )
              goto LABEL_16;
          }
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
            (int)L"WdipReadParameterCollectionFromFile",
            1057,
            (int)L"Error = %d",
            5);
          v14 = 0;
          v5 = -2147467259;
          v17 = 0;
          v15 = 0;
          do
          {
            v16 = &v9[v15];
            if ( *v16 )
            {
              WdipDeleteParameter(v16);
              v9[v17] = 0;
              v14 = v17;
            }
            v17 = ++v14;
            v15 = v14;
          }
          while ( v14 < v10 );
          WdipFree(v9);
        }
        else
        {
LABEL_16:
          *(_DWORD *)a1 = Buffer;
          *(_QWORD *)(a1 + 8) = v9;
          *(_DWORD *)(a1 + 4) = v10;
        }
      }
      else
      {
        v5 = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
          (int)L"WdipReadParameterCollectionFromFile",
          1048,
          (int)L"Error = %d",
          14);
      }
    }
    else
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
        (int)L"WdipReadParameterCollectionFromFile",
        1045,
        (int)L"Error = %d",
        v7);
    }
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterCollectionFromFile",
      1037,
      (int)L"Error = %d",
      Args);
  }
  return v5;
}

```

## disassembly

```asm
0x180018680  mov     [rsp-28h+arg_0], rbx
0x180018685  push    rbp
0x180018686  push    rsi
0x180018687  push    rdi
0x180018688  push    r14
0x18001868a  push    r15
0x18001868c  mov     rbp, rsp
0x18001868f  sub     rsp, 30h
0x180018693  mov     [rbp+arg_10], 0
0x18001869a  mov     r14, rdx
0x18001869d  mov     [rbp+arg_8], 0
0x1800186a4  mov     rsi, rcx
0x1800186a7  mov     [rbp+Buffer], 0
0x1800186ae  test    rdx, rdx
0x1800186b1  jnz     short loc_1800186E5
0x1800186b3  mov     r8d, 404h; int
0x1800186b9  mov     dword ptr [rsp+30h+Args], 57h ; 'W'; Args
0x1800186c1  mov     ebx, 80070057h
0x1800186c6  lea     r9, aErrorD; "Error = %d"
0x1800186cd  lea     rdx, aWdipreadparame_0; "WdipReadParameterCollectionFromFile"
0x1800186d4  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800186db  call    WdipTraceError
0x1800186e0  jmp     loc_1800187C8
0x1800186e5  test    rsi, rsi
0x1800186e8  jnz     short loc_1800186F2
0x1800186ea  mov     r8d, 405h
0x1800186f0  jmp     short loc_1800186B9
0x1800186f2  mov     edi, 4
0x1800186f7  lea     r9, [rbp+arg_10]
0x1800186fb  mov     r8d, edi; nNumberOfBytesToRead
0x1800186fe  lea     rdx, [rbp+Buffer]; lpBuffer
0x180018702  mov     rcx, r14; hFile
0x180018705  call    WdipReadFile
0x18001870a  mov     ebx, eax
0x18001870c  test    eax, eax
0x18001870e  jns     short loc_18001871F
0x180018710  movzx   ecx, ax
0x180018713  mov     r8d, 40Dh
0x180018719  mov     dword ptr [rsp+30h+Args], ecx
0x18001871d  jmp     short loc_1800186C6
0x18001871f  lea     r9, [rbp+arg_10]
0x180018723  mov     r8d, edi; nNumberOfBytesToRead
0x180018726  lea     rdx, [rbp+arg_8]; lpBuffer
0x18001872a  mov     rcx, r14; hFile
0x18001872d  call    WdipReadFile
0x180018732  mov     ebx, eax
0x180018734  test    eax, eax
0x180018736  jns     short loc_18001874A
0x180018738  movzx   eax, ax
0x18001873b  mov     r8d, 415h
0x180018741  mov     dword ptr [rsp+30h+Args], eax
0x180018745  jmp     loc_1800186C6
0x18001874a  mov     ecx, [rbp+arg_8]
0x18001874d  shl     rcx, 3
0x180018751  call    WdipAlloc
0x180018756  mov     rdi, rax
0x180018759  test    rax, rax
0x18001875c  jnz     short loc_180018776
0x18001875e  mov     ebx, 8007000Eh
0x180018763  mov     dword ptr [rsp+30h+Args], 0Eh
0x18001876b  mov     r8d, 418h
0x180018771  jmp     loc_1800186C6
0x180018776  mov     r8d, [rbp+arg_8]
0x18001877a  xor     edx, edx; Val
0x18001877c  shl     r8, 3; Size
0x180018780  mov     rcx, rdi; void *
0x180018783  call    memset_0
0x180018788  mov     r15d, [rbp+arg_8]
0x18001878c  mov     [rbp+arg_8], 0
0x180018793  test    r15d, r15d
0x180018796  jz      short loc_1800187BB
0x180018798  mov     rcx, r14; hFile
0x18001879b  call    ?WdipReadParameterFromFile@@YAPEAU__WDIP_PARAMETER@@PEAX@Z; WdipReadParameterFromFile(void *)
0x1800187a0  mov     ecx, [rbp+arg_8]
0x1800187a3  mov     [rdi+rcx*8], rax
0x1800187a7  mov     ecx, [rbp+arg_8]
0x1800187aa  cmp     qword ptr [rdi+rcx*8], 0
0x1800187af  jz      short loc_1800187DB
0x1800187b1  inc     ecx
0x1800187b3  mov     [rbp+arg_8], ecx
0x1800187b6  cmp     ecx, r15d
0x1800187b9  jb      short loc_180018798
0x1800187bb  mov     eax, [rbp+Buffer]
0x1800187be  mov     [rsi], eax
0x1800187c0  mov     [rsi+8], rdi
0x1800187c4  mov     [rsi+4], r15d
0x1800187c8  mov     eax, ebx
0x1800187ca  mov     rbx, [rsp+30h+arg_0]
0x1800187cf  add     rsp, 30h
0x1800187d3  pop     r15
0x1800187d5  pop     r14
0x1800187d7  pop     rdi
0x1800187d8  pop     rsi
0x1800187d9  pop     rbp
0x1800187da  retn
0x1800187db  lea     r9, aErrorD; "Error = %d"
0x1800187e2  mov     dword ptr [rsp+30h+Args], 4005h; Args
0x1800187ea  mov     r8d, 421h; int
0x1800187f0  lea     rdx, aWdipreadparame_0; "WdipReadParameterCollectionFromFile"
0x1800187f7  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800187fe  call    WdipTraceError
0x180018803  xor     edx, edx
0x180018805  mov     ebx, 80004005h
0x18001880a  mov     [rbp+arg_8], edx
0x18001880d  xor     eax, eax
0x18001880f  lea     rcx, [rdi+rax*8]
0x180018813  cmp     qword ptr [rcx], 0
0x180018817  jz      short loc_18001882C
0x180018819  call    WdipDeleteParameter
0x18001881e  mov     eax, [rbp+arg_8]
0x180018821  mov     qword ptr [rdi+rax*8], 0
0x180018829  mov     edx, [rbp+arg_8]
0x18001882c  inc     edx
0x18001882e  mov     [rbp+arg_8], edx
0x180018831  mov     eax, edx
0x180018833  cmp     edx, r15d
0x180018836  jb      short loc_18001880F
0x180018838  mov     rcx, rdi
0x18001883b  call    WdipFree
0x180018840  jmp     short loc_1800187C8
```
