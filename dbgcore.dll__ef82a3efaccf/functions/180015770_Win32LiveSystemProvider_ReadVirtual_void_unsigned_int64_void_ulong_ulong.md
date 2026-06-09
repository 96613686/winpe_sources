# Win32LiveSystemProvider::ReadVirtual(void *,unsigned __int64,void *,ulong,ulong *)

- ea: `0x180015770`
- end: `0x180015934`
- name: `?ReadVirtual@Win32LiveSystemProvider@@UEAAJPEAX_K0KPEAK@Z`
- size: `452`
- prototype: `int(Win32LiveSystemProvider *__hidden this, void *, unsigned __int64, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022890`

## callees

- `0x180015770`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001587a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001587a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015884`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180015863`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180015863`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::ReadVirtual(
        Win32LiveSystemProvider *this,
        void *a2,
        __int64 a3,
        char *a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned int v6; // esi
  unsigned int v7; // edi
  signed int v8; // ebx
  void *v11; // r10
  unsigned int v13; // r14d
  __int64 (__fastcall *v14)(_QWORD, void *, __int64, char *, unsigned int, unsigned int *); // rax
  unsigned int v15; // r9d
  int v16; // ecx
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // ecx
  signed int LastError; // eax
  __int64 (__fastcall *v21)(_QWORD, void *, __int64, char *, unsigned int, unsigned int *, signed int); // rax
  signed int v22; // eax
  SIZE_T NumberOfBytesRead; // [rsp+90h] [rbp+50h] BYREF

  v6 = a5;
  v7 = 0;
  v8 = 0;
  NumberOfBytesRead = 0;
  v11 = a2;
  v13 = -2147024597;
  if ( a5 )
  {
    while ( !v8 )
    {
      v14 = (__int64 (__fastcall *)(_QWORD, void *, __int64, char *, unsigned int, unsigned int *))*((_QWORD *)this + 3);
      v15 = 0;
      v16 = 0;
      a5 = 0;
      if ( v14 )
      {
        v17 = v14(*((_QWORD *)this + 5), v11, a3, a4, v6 - v7, &a5);
        v15 = a5;
        v16 = v17;
        v11 = a2;
        if ( !v17 && a5 >= v6 - v7 )
        {
          v15 = v6 - v7;
          a5 = v6 - v7;
        }
      }
      if ( v15 + v7 >= v6 )
      {
        v7 += v15;
        break;
      }
      if ( ((v16 + 0x80000000) & 0x80000000) != 0 || v16 == -2147467263 )
      {
        v18 = v6 - v15 - v7;
        if ( 4096 - (((_WORD)v15 + (_WORD)a3) & 0xFFFu) < v18 )
          v18 = 4096 - (((_WORD)v15 + (_WORD)a3) & 0xFFF);
        if ( ReadProcessMemory(v11, (LPCVOID)(v15 + a3), &a4[v15], v18, &NumberOfBytesRead) )
        {
          v19 = NumberOfBytesRead + a5;
          a5 += NumberOfBytesRead;
          v8 = 0;
        }
        else
        {
          if ( GetLastError() )
          {
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v8 = -2147467259;
          }
          v19 = a5;
        }
        v21 = (__int64 (__fastcall *)(_QWORD, void *, __int64, char *, unsigned int, unsigned int *, signed int))*((_QWORD *)this + 4);
        if ( v21 )
        {
          v22 = v21(*((_QWORD *)this + 5), a2, a3, a4, v6 - v7, &a5, v8);
          v19 = a5;
          if ( v22 != -2147467263 )
            v8 = v22;
        }
        if ( v8 >= 0 && !v19 )
          v8 = -2147024597;
        v11 = a2;
        v7 += v19;
        a3 += v19;
        a4 += v19;
        if ( v7 < v6 )
          continue;
      }
      break;
    }
  }
  *a6 = v7;
  if ( v7 || !v6 )
    return 0;
  return v13;
}

```

## disassembly

```asm
0x180015770  mov     [rsp-38h+arg_0], rbx
0x180015775  mov     [rsp-38h+arg_8], rdx
0x18001577a  push    rbp
0x18001577b  push    rsi
0x18001577c  push    rdi
0x18001577d  push    r12
0x18001577f  push    r13
0x180015781  push    r14
0x180015783  push    r15
0x180015785  mov     rbp, rsp
0x180015788  sub     rsp, 40h
0x18001578c  mov     esi, [rbp+arg_20]
0x18001578f  xor     edi, edi
0x180015791  xor     ebx, ebx
0x180015793  mov     [rbp+NumberOfBytesRead], rdi
0x180015797  mov     r12, r9
0x18001579a  mov     r15, r8
0x18001579d  mov     r10, rdx
0x1800157a0  mov     r13, rcx
0x1800157a3  mov     r14d, 8007012Bh
0x1800157a9  test    esi, esi
0x1800157ab  jz      loc_180015908
0x1800157b1  mov     edx, 80000000h
0x1800157b6  test    ebx, ebx
0x1800157b8  jnz     loc_180015908
0x1800157be  mov     rax, [r13+18h]
0x1800157c2  xor     r9d, r9d
0x1800157c5  xor     ecx, ecx
0x1800157c7  mov     [rbp+arg_20], r9d
0x1800157cb  test    rax, rax
0x1800157ce  jz      short loc_180015811
0x1800157d0  lea     rcx, [rbp+arg_20]
0x1800157d4  mov     ebx, esi
0x1800157d6  mov     [rsp+40h+var_18], rcx
0x1800157db  sub     ebx, edi
0x1800157dd  mov     rcx, [r13+28h]
0x1800157e1  mov     r9, r12
0x1800157e4  mov     r8, r15
0x1800157e7  mov     dword ptr [rsp+40h+lpNumberOfBytesRead], ebx
0x1800157eb  mov     rdx, r10
0x1800157ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157f3  mov     r9d, [rbp+arg_20]
0x1800157f7  mov     ecx, eax
0x1800157f9  mov     r10, [rbp+arg_8]
0x1800157fd  mov     edx, 80000000h
0x180015802  test    eax, eax
0x180015804  jnz     short loc_180015811
0x180015806  cmp     r9d, ebx
0x180015809  jb      short loc_180015811
0x18001580b  mov     r9d, ebx
0x18001580e  mov     [rbp+arg_20], ebx
0x180015811  lea     eax, [r9+rdi]
0x180015815  cmp     eax, esi
0x180015817  jnb     loc_180015906
0x18001581d  lea     eax, [rcx+rdx]
0x180015820  test    edx, eax
0x180015822  jnz     short loc_180015830
0x180015824  cmp     ecx, 80004001h
0x18001582a  jnz     loc_180015908
0x180015830  mov     r8d, r9d
0x180015833  mov     ecx, 1000h
0x180015838  lea     rdx, [r8+r15]; lpBaseAddress
0x18001583c  mov     eax, edx
0x18001583e  and     eax, 0FFFh
0x180015843  sub     ecx, eax
0x180015845  mov     eax, esi
0x180015847  sub     eax, r9d
0x18001584a  sub     eax, edi
0x18001584c  cmp     ecx, eax
0x18001584e  cmovb   eax, ecx
0x180015851  add     r8, r12; lpBuffer
0x180015854  mov     r9d, eax; nSize
0x180015857  mov     rcx, r10; hProcess
0x18001585a  lea     rax, [rbp+NumberOfBytesRead]
0x18001585e  mov     [rsp+40h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180015863  call    cs:__imp_ReadProcessMemory
0x180015869  test    eax, eax
0x18001586b  jz      short loc_18001587A
0x18001586d  mov     ecx, [rbp+arg_20]
0x180015870  add     ecx, dword ptr [rbp+NumberOfBytesRead]
0x180015873  mov     [rbp+arg_20], ecx
0x180015876  xor     ebx, ebx
0x180015878  jmp     short loc_1800158A3
0x18001587a  call    cs:__imp_GetLastError
0x180015880  test    eax, eax
0x180015882  jz      short loc_18001589B
0x180015884  call    cs:__imp_GetLastError
0x18001588a  mov     ebx, eax
0x18001588c  test    eax, eax
0x18001588e  jle     short loc_1800158A0
0x180015890  movzx   ebx, ax
0x180015893  or      ebx, 80070000h
0x180015899  jmp     short loc_1800158A0
0x18001589b  mov     ebx, 80004005h
0x1800158a0  mov     ecx, [rbp+arg_20]
0x1800158a3  mov     rax, [r13+20h]
0x1800158a7  test    rax, rax
0x1800158aa  jz      short loc_1800158DF
0x1800158ac  mov     ecx, esi
0x1800158ae  mov     [rsp+40h+var_10], ebx
0x1800158b2  sub     ecx, edi
0x1800158b4  lea     rdx, [rbp+arg_20]
0x1800158b8  mov     [rsp+40h+var_18], rdx
0x1800158bd  mov     r9, r12
0x1800158c0  mov     rdx, [rbp+arg_8]
0x1800158c4  mov     r8, r15
0x1800158c7  mov     dword ptr [rsp+40h+lpNumberOfBytesRead], ecx
0x1800158cb  mov     rcx, [r13+28h]
0x1800158cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158d4  mov     ecx, [rbp+arg_20]
0x1800158d7  cmp     eax, 80004001h
0x1800158dc  cmovnz  ebx, eax
0x1800158df  test    ebx, ebx
0x1800158e1  js      short loc_1800158E9
0x1800158e3  test    ecx, ecx
0x1800158e5  cmovz   ebx, r14d
0x1800158e9  mov     r10, [rbp+arg_8]
0x1800158ed  add     edi, ecx
0x1800158ef  mov     eax, ecx
0x1800158f1  mov     edx, 80000000h
0x1800158f6  add     r15, rax
0x1800158f9  add     r12, rax
0x1800158fc  cmp     edi, esi
0x1800158fe  jb      loc_1800157B6
0x180015904  jmp     short loc_180015908
0x180015906  mov     edi, eax
0x180015908  mov     rax, [rbp+arg_28]
0x18001590c  mov     [rax], edi
0x18001590e  test    edi, edi
0x180015910  jnz     short loc_180015916
0x180015912  test    esi, esi
0x180015914  jnz     short loc_180015919
0x180015916  xor     r14d, r14d
0x180015919  mov     rbx, [rsp+40h+arg_0]
0x180015921  mov     eax, r14d
0x180015924  add     rsp, 40h
0x180015928  pop     r15
0x18001592a  pop     r14
0x18001592c  pop     r13
0x18001592e  pop     r12
0x180015930  pop     rdi
0x180015931  pop     rsi
0x180015932  pop     rbp
0x180015933  retn
```
