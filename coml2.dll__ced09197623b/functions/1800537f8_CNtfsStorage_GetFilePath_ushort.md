# CNtfsStorage::GetFilePath(ushort * *)

- ea: `0x1800537f8`
- end: `0x180053902`
- name: `?GetFilePath@CNtfsStorage@@AEAAJPEAPEAG@Z`
- size: `266`
- prototype: `__int64 __fastcall(CNtfsStorage *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180054b10`

## callees

- `0x1800341f4`
- `0x1800537f8`
- `0x18006141c`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180053847`
- `ntdll!NtQueryInformationFile` at `0x180053847`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800538ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800538ef`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18005389e`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18005389e`

## pseudocode

```c
__int64 __fastcall CNtfsStorage::GetFilePath(CNtfsStorage *this, unsigned __int16 **a2)
{
  unsigned int *v4; // rax
  unsigned int *v5; // rdi
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  unsigned __int16 *v8; // rsi
  __int16 v9; // cx
  __int16 v10; // ax
  __int64 v11; // rbp
  unsigned __int64 v12; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-38h] BYREF

  IoStatusBlock = 0;
  v4 = (unsigned int *)CoTaskMemAlloc(0x212u);
  v5 = v4;
  if ( v4 )
  {
    v7 = NtQueryInformationFile(*((HANDLE *)this + 13), &IoStatusBlock, v4, 0x212u, FileNameInformation);
    if ( v7 >= 0 )
    {
      if ( *v5 )
      {
        v8 = (unsigned __int16 *)CoTaskMemAlloc((int)(*v5 + 6));
        if ( v8 )
        {
          v6 = -2147467259;
          if ( IsCharAlphaW(*((_WORD *)this + 38)) )
          {
            v9 = *((_WORD *)this + 38);
            v8[2] = 0;
            v10 = 58;
            v11 = 2;
          }
          else
          {
            v10 = 0;
            v9 = 92;
            v11 = 1;
          }
          *v8 = v9;
          v8[1] = v10;
          memcpy_0(&v8[v11], v5 + 1, *v5);
          v12 = v11 + ((unsigned __int64)*v5 >> 1);
          *a2 = v8;
          v8[v12] = 0;
        }
        else
        {
          v6 = -2147287032;
        }
      }
      else
      {
        v6 = -2147286789;
      }
    }
    else if ( v7 == -2147483643 )
    {
      v6 = -2147417803;
    }
    else
    {
      v6 = NtStatusToScode(v7);
    }
    CoTaskMemFree(v5);
  }
  else
  {
    return (unsigned int)-2147287032;
  }
  return v6;
}

```

## disassembly

```asm
0x1800537f8  push    rbx
0x1800537fa  push    rbp
0x1800537fb  push    rsi
0x1800537fc  push    rdi
0x1800537fd  push    r14
0x1800537ff  sub     rsp, 40h
0x180053803  mov     rbp, rcx
0x180053806  xorps   xmm0, xmm0
0x180053809  mov     ebx, 212h
0x18005380e  mov     r14, rdx
0x180053811  mov     ecx, ebx; cb
0x180053813  movups  xmmword ptr [rsp+68h+IoStatusBlock], xmm0
0x180053818  call    cs:__imp_CoTaskMemAlloc
0x18005381e  mov     rdi, rax
0x180053821  test    rax, rax
0x180053824  jnz     short loc_180053830
0x180053826  mov     ebx, 80030008h
0x18005382b  jmp     loc_1800538F5
0x180053830  mov     rcx, [rbp+68h]; FileHandle
0x180053834  lea     rdx, [rsp+68h+IoStatusBlock]; IoStatusBlock
0x180053839  mov     r9d, ebx; Length
0x18005383c  mov     [rsp+68h+FileInformationClass], 9; FileInformationClass
0x180053844  mov     r8, rdi; FileInformation
0x180053847  call    cs:__imp_NtQueryInformationFile
0x18005384d  test    eax, eax
0x18005384f  jns     short loc_18005386D
0x180053851  cmp     eax, 80000005h
0x180053856  jnz     short loc_180053862
0x180053858  mov     ebx, 80010135h
0x18005385d  jmp     loc_1800538EC
0x180053862  mov     ecx, eax; int
0x180053864  call    ?NtStatusToScode@@YAJJ@Z; NtStatusToScode(long)
0x180053869  mov     ebx, eax
0x18005386b  jmp     short loc_1800538EC
0x18005386d  mov     eax, [rdi]
0x18005386f  test    eax, eax
0x180053871  jnz     short loc_18005387A
0x180053873  mov     ebx, 800300FBh
0x180053878  jmp     short loc_1800538EC
0x18005387a  add     eax, 6
0x18005387d  movsxd  rcx, eax; cb
0x180053880  call    cs:__imp_CoTaskMemAlloc
0x180053886  mov     rsi, rax
0x180053889  test    rax, rax
0x18005388c  jnz     short loc_180053895
0x18005388e  mov     ebx, 80030008h
0x180053893  jmp     short loc_1800538EC
0x180053895  movzx   ecx, word ptr [rbp+4Ch]; ch
0x180053899  mov     ebx, 80004005h
0x18005389e  call    cs:__imp_IsCharAlphaW
0x1800538a4  test    eax, eax
0x1800538a6  jz      short loc_1800538BC
0x1800538a8  movzx   ecx, word ptr [rbp+4Ch]
0x1800538ac  xor     eax, eax
0x1800538ae  mov     [rsi+4], ax
0x1800538b2  mov     eax, 3Ah ; ':'
0x1800538b7  lea     ebp, [rax-38h]
0x1800538ba  jmp     short loc_1800538C4
0x1800538bc  xor     eax, eax
0x1800538be  lea     ecx, [rax+5Ch]
0x1800538c1  lea     ebp, [rax+1]
0x1800538c4  mov     [rsi], cx
0x1800538c7  lea     rdx, [rdi+4]; Src
0x1800538cb  mov     [rsi+2], ax
0x1800538cf  lea     rcx, [rsi+rbp*2]; void *
0x1800538d3  mov     r8d, [rdi]; Size
0x1800538d6  call    memcpy_0
0x1800538db  mov     ecx, [rdi]
0x1800538dd  shr     rcx, 1
0x1800538e0  add     rcx, rbp
0x1800538e3  mov     [r14], rsi
0x1800538e6  xor     eax, eax
0x1800538e8  mov     [rsi+rcx*2], ax
0x1800538ec  mov     rcx, rdi; pv
0x1800538ef  call    cs:__imp_CoTaskMemFree
0x1800538f5  mov     eax, ebx
0x1800538f7  add     rsp, 40h
0x1800538fb  pop     r14
0x1800538fd  pop     rdi
0x1800538fe  pop     rsi
0x1800538ff  pop     rbp
0x180053900  pop     rbx
0x180053901  retn
```
