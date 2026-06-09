# ATL::CComDynamicUnkArray::Add(IUnknown *)

- ea: `0x18000939c`
- end: `0x1800094bb`
- name: `?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z`
- size: `287`
- prototype: `unsigned int __fastcall(ATL::CComDynamicUnkArray *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800094f0`

## callees

- `0x18000939c`
- `0x18002737e`

## import_xrefs

- `msvcrt!malloc` at `0x1800093d7`
- `msvcrt!malloc` at `0x1800093d7`
- `msvcrt!realloc` at `0x18000946d`
- `msvcrt!realloc` at `0x18000946d`

## pseudocode

```c
__int64 __fastcall ATL::CComDynamicUnkArray::Add(ATL::CComDynamicUnkArray *this, struct IUnknown *a2)
{
  int v2; // r8d
  ATL::CComDynamicUnkArray *v4; // rbx
  __int64 result; // rax
  _QWORD *v6; // rax
  __int64 v7; // rdx
  unsigned __int64 v8; // rax
  int v9; // edi
  char *v10; // rcx
  __int64 v11; // rax

  v2 = *((_DWORD *)this + 2);
  v4 = this;
  if ( !v2 )
  {
    *(_QWORD *)this = a2;
    result = 1;
    *((_DWORD *)this + 2) = 1;
    return result;
  }
  if ( v2 == 1 )
  {
    v6 = malloc(0x20u);
    if ( !v6 )
      return 0;
    v6[1] = 0;
    v2 = 4;
    v6[2] = 0;
    v6[3] = 0;
    *v6 = *(_QWORD *)v4;
    *(_QWORD *)v4 = v6;
    *((_DWORD *)v4 + 2) = 4;
  }
  else if ( v2 < 2 )
  {
    goto LABEL_8;
  }
  this = *(ATL::CComDynamicUnkArray **)v4;
LABEL_8:
  v7 = 8LL * v2;
  while ( 1 )
  {
    v8 = v2 >= 2 ? v7 + *(_QWORD *)v4 : (unsigned __int64)v4 + v7;
    if ( (unsigned __int64)this >= v8 )
      break;
    if ( !*(_QWORD *)this )
    {
      *(_QWORD *)this = a2;
      if ( *((int *)v4 + 2) >= 2 )
        v4 = *(ATL::CComDynamicUnkArray **)v4;
      return (unsigned int)((this - v4) >> 3) + 1;
    }
    this = (ATL::CComDynamicUnkArray *)((char *)this + 8);
  }
  v9 = 2 * *((_DWORD *)v4 + 2);
  v10 = (char *)realloc(*(void **)v4, 8LL * v9);
  if ( !v10 )
    return 0;
  v11 = *((int *)v4 + 2);
  *(_QWORD *)v4 = v10;
  memset_0(&v10[8 * v11], 0, 8 * v11);
  *(_QWORD *)(*(_QWORD *)v4 + 8LL * *((int *)v4 + 2)) = a2;
  result = (unsigned int)(*((_DWORD *)v4 + 2) + 1);
  *((_DWORD *)v4 + 2) = v9;
  return result;
}

```

## disassembly

```asm
0x18000939c  mov     [rsp+arg_0], rbx
0x1800093a1  mov     [rsp+arg_8], rsi
0x1800093a6  push    rdi
0x1800093a7  sub     rsp, 20h
0x1800093ab  mov     r8d, [rcx+8]
0x1800093af  mov     rsi, rdx
0x1800093b2  mov     rbx, rcx
0x1800093b5  test    r8d, r8d
0x1800093b8  jnz     short loc_1800093CD
0x1800093ba  mov     [rcx], rdx
0x1800093bd  lea     eax, [r8+1]
0x1800093c1  mov     dword ptr [rcx+8], 1
0x1800093c8  jmp     loc_1800094AB
0x1800093cd  cmp     r8d, 1
0x1800093d1  jnz     short loc_180009413
0x1800093d3  lea     ecx, [r8+1Fh]; Size
0x1800093d7  call    cs:__imp_malloc
0x1800093dd  test    rax, rax
0x1800093e0  jz      loc_18000947B
0x1800093e6  mov     qword ptr [rax+8], 0
0x1800093ee  mov     r8d, 4
0x1800093f4  mov     qword ptr [rax+10h], 0
0x1800093fc  mov     qword ptr [rax+18h], 0
0x180009404  mov     rcx, [rbx]
0x180009407  mov     [rax], rcx
0x18000940a  mov     [rbx], rax
0x18000940d  mov     [rbx+8], r8d
0x180009411  jmp     short loc_180009419
0x180009413  cmp     r8d, 2
0x180009417  jl      short loc_18000941C
0x180009419  mov     rcx, [rbx]
0x18000941c  movsxd  rdx, r8d
0x18000941f  shl     rdx, 3
0x180009423  cmp     r8d, 2
0x180009427  jge     short loc_18000942F
0x180009429  lea     rax, [rdx+rbx]
0x18000942d  jmp     short loc_180009435
0x18000942f  mov     rax, [rbx]
0x180009432  add     rax, rdx
0x180009435  cmp     rcx, rax
0x180009438  jnb     short loc_18000945E
0x18000943a  cmp     qword ptr [rcx], 0
0x18000943e  jz      short loc_180009446
0x180009440  add     rcx, 8
0x180009444  jmp     short loc_180009423
0x180009446  mov     [rcx], rsi
0x180009449  cmp     dword ptr [rbx+8], 2
0x18000944d  jl      short loc_180009452
0x18000944f  mov     rbx, [rbx]
0x180009452  sub     rcx, rbx
0x180009455  sar     rcx, 3
0x180009459  lea     eax, [rcx+1]
0x18000945c  jmp     short loc_1800094AB
0x18000945e  mov     edi, [rbx+8]
0x180009461  mov     rcx, [rbx]; Block
0x180009464  add     edi, edi
0x180009466  movsxd  rdx, edi
0x180009469  shl     rdx, 3; Size
0x18000946d  call    cs:__imp_realloc
0x180009473  mov     rcx, rax
0x180009476  test    rax, rax
0x180009479  jnz     short loc_18000947F
0x18000947b  xor     eax, eax
0x18000947d  jmp     short loc_1800094AB
0x18000947f  movsxd  rax, dword ptr [rbx+8]
0x180009483  xor     edx, edx; Val
0x180009485  mov     [rbx], rcx
0x180009488  lea     r8, ds:0[rax*8]; Size
0x180009490  add     rcx, r8; void *
0x180009493  call    memset_0
0x180009498  movsxd  rcx, dword ptr [rbx+8]
0x18000949c  mov     rax, [rbx]
0x18000949f  mov     [rax+rcx*8], rsi
0x1800094a3  mov     eax, [rbx+8]
0x1800094a6  inc     eax
0x1800094a8  mov     [rbx+8], edi
0x1800094ab  mov     rbx, [rsp+28h+arg_0]
0x1800094b0  mov     rsi, [rsp+28h+arg_8]
0x1800094b5  add     rsp, 20h
0x1800094b9  pop     rdi
0x1800094ba  retn
```
