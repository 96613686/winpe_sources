# PlaiIsLocalServer(ushort const *,int *)

- ea: `0x180039e30`
- end: `0x18003a16f`
- name: `?PlaiIsLocalServer@@YAJPEBGPEAH@Z`
- size: `831`
- prototype: `__int64 __fastcall(wchar_t *String2, int *)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007d980`
- `0x1800f4804`
- `0x1800f6a78`
- `0x18012e71c`
- `0x18012f530`
- `0x180130b28`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18002b3a0`
- `0x180039e30`
- `0x18013aee0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003a0b5`
- `msvcrt!_wcsicmp` at `0x18003a14e`
- `msvcrt!_wcsicmp` at `0x18003a0b5`
- `msvcrt!_wcsicmp` at `0x18003a14e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a121`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18003a113`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18003a113`

## pseudocode

```c
__int64 __fastcall PlaiIsLocalServer(wchar_t *String2, int *a2)
{
  wchar_t *v3; // rbx
  __int64 result; // rax
  __int64 v5; // rax
  bool v6; // zf
  __int64 v7; // rax
  WCHAR *v8; // rax
  const wchar_t *v9; // rbp
  unsigned int v10; // esi
  DWORD LastError; // eax
  int v12; // eax
  int v13; // [rsp+20h] [rbp-198h]
  int v14; // [rsp+70h] [rbp-148h] BYREF
  int v15; // [rsp+78h] [rbp-140h] BYREF
  DWORD nSize[4]; // [rsp+80h] [rbp-138h] BYREF
  unsigned __int16 v17[64]; // [rsp+90h] [rbp-128h] BYREF
  unsigned __int16 v18[64]; // [rsp+110h] [rbp-A8h] BYREF

  nSize[0] = 16;
  v3 = String2;
  if ( !String2 || !*String2 )
  {
    result = 0;
    *a2 = 1;
    return result;
  }
  if ( _wcsicmp(String2, L".") )
  {
    v8 = (WCHAR *)PlaiAlloc(2LL * nSize[0], 1, 0, byte_180147320, v13);
    v9 = v8;
    if ( v8 )
    {
      if ( GetComputerNameW(v8, nSize) )
      {
        v10 = 0;
      }
      else
      {
        LastError = GetLastError();
        v12 = PlaiHResultFromWin32(LastError);
        v10 = v12;
        if ( v12 < 0 )
        {
          v15 = 0;
          v14 = v12;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v18, 0x4000000000000800uLL);
            v7 = -1;
            do
              v6 = v18[++v7] == 0;
            while ( !v6 );
            EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v14);
          }
          *a2 = 1;
          goto LABEL_15;
        }
      }
      for ( ; *v3 == 92; ++v3 )
        ;
      *a2 = _wcsicmp(v9, v3) == 0;
LABEL_15:
      PlaiFree(v9, 1);
      return v10;
    }
    v14 = 0;
    v15 = -2147024882;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v17, 0x4000000000000800uLL);
      v5 = -1;
      do
        v6 = v17[++v5] == 0;
      while ( !v6 );
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v15);
    }
    *a2 = 1;
    return 2147942414LL;
  }
  else
  {
    *a2 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x180039e30  push    rbx
0x180039e32  push    rdi
0x180039e33  sub     rsp, 1A8h
0x180039e3a  mov     rax, cs:__security_cookie
0x180039e41  xor     rax, rsp
0x180039e44  mov     [rsp+1B8h+var_28], rax
0x180039e4c  mov     [rsp+1B8h+nSize], 10h
0x180039e57  mov     rdi, rdx
0x180039e5a  mov     rbx, rcx
0x180039e5d  test    rcx, rcx
0x180039e60  jz      short loc_180039E6D
0x180039e62  xor     eax, eax
0x180039e64  cmp     ax, [rcx]
0x180039e67  jnz     loc_18003A0AE
0x180039e6d  xor     eax, eax
0x180039e6f  mov     dword ptr [rdx], 1
0x180039e75  mov     rcx, [rsp+1B8h+var_28]
0x180039e7d  xor     rcx, rsp; StackCookie
0x180039e80  call    __security_check_cookie
0x180039e85  add     rsp, 1A8h
0x180039e8c  pop     rdi
0x180039e8d  pop     rbx
0x180039e8e  retn
0x180039e8f  mov     rax, cs:qword_180169748
0x180039e96  and     rax, rdx
0x180039e99  cmp     cs:qword_180169748, rax
0x180039ea0  jnz     loc_180039F44
0x180039ea6  lea     rcx, [rsp+1B8h+var_128]; unsigned __int16 *
0x180039eae  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180039eb3  lea     rcx, [rsp+1B8h+var_128]
0x180039ebb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180039ec2  cmp     word ptr [rcx+rax*2+2], 0
0x180039ec8  lea     rax, [rax+1]
0x180039ecc  jnz     short loc_180039EC2
0x180039ece  lea     ecx, [rax+rax]
0x180039ed1  mov     r8d, 5
0x180039ed7  add     rcx, 2
0x180039edb  lea     rax, [rsp+1B8h+var_128]
0x180039ee3  mov     [rsp+1B8h+var_158], rcx
0x180039ee8  lea     r9, [rsp+1B8h+var_140]
0x180039eed  mov     [rsp+1B8h+var_160], rax
0x180039ef2  lea     rdx, PLA_EVENT_ERROR
0x180039ef9  mov     [rsp+1B8h+var_168], 12h
0x180039f02  lea     rax, aPlaiislocalser; "PlaiIsLocalServer"
0x180039f09  mov     [rsp+1B8h+var_170], rax
0x180039f0e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180039f15  mov     [rsp+1B8h+var_178], 4
0x180039f1e  lea     rax, [rsp+1B8h+var_148]
0x180039f23  mov     [rsp+1B8h+var_180], rax
0x180039f28  mov     [rsp+1B8h+var_188], 1
0x180039f31  mov     [rsp+1B8h+var_190], r14
0x180039f36  mov     [rsp+1B8h+var_198], 4
0x180039f3f  call    EventingWriteEvent
0x180039f44  mov     dword ptr [rdi], 1
0x180039f4a  mov     eax, 8007000Eh
0x180039f4f  mov     rbp, [rsp+1B8h+arg_10]
0x180039f57  mov     r14, [rsp+1B8h+var_18]
0x180039f5f  jmp     loc_180039E75
0x180039f64  mov     rax, cs:qword_180169748
0x180039f6b  and     rax, rdx
0x180039f6e  cmp     cs:qword_180169748, rax
0x180039f75  jnz     loc_18003A022
0x180039f7b  lea     rcx, [rsp+1B8h+var_A8]; unsigned __int16 *
0x180039f83  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180039f88  lea     rcx, [rsp+1B8h+var_A8]
0x180039f90  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180039f97  nop     word ptr [rax+rax+00000000h]
0x180039fa0  cmp     word ptr [rcx+rax*2+2], 0
0x180039fa6  lea     rax, [rax+1]
0x180039faa  jnz     short loc_180039FA0
0x180039fac  lea     ecx, [rax+rax]
0x180039faf  mov     r8d, 5
0x180039fb5  add     rcx, 2
0x180039fb9  lea     rax, [rsp+1B8h+var_A8]
0x180039fc1  mov     [rsp+1B8h+var_158], rcx
0x180039fc6  lea     r9, [rsp+1B8h+var_148]
0x180039fcb  mov     [rsp+1B8h+var_160], rax
0x180039fd0  lea     rdx, PLA_EVENT_ERROR
0x180039fd7  mov     [rsp+1B8h+var_168], 12h
0x180039fe0  lea     rax, aPlaiislocalser; "PlaiIsLocalServer"
0x180039fe7  mov     [rsp+1B8h+var_170], rax
0x180039fec  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180039ff3  mov     [rsp+1B8h+var_178], 4
0x180039ffc  lea     rax, [rsp+1B8h+var_140]
0x18003a001  mov     [rsp+1B8h+var_180], rax
0x18003a006  mov     [rsp+1B8h+var_188], 1
0x18003a00f  mov     [rsp+1B8h+var_190], r14
0x18003a014  mov     [rsp+1B8h+var_198], 4
0x18003a01d  call    EventingWriteEvent
0x18003a022  mov     dword ptr [rdi], 1
0x18003a028  mov     edx, 1; int
0x18003a02d  mov     rcx, rbp; lpMem
0x18003a030  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18003a035  mov     eax, esi
0x18003a037  mov     rsi, [rsp+1B8h+arg_18]
0x18003a03f  jmp     loc_180039F4F
0x18003a044  cmp     dword ptr cs:xmmword_180169738, 0
0x18003a04b  mov     [rsp+1B8h+var_148], 0
0x18003a053  mov     [rsp+1B8h+var_140], 8007000Eh
0x18003a05b  jz      loc_180039F44
0x18003a061  mov     rdx, 4000000000000800h; unsigned __int64
0x18003a06b  test    qword ptr cs:xmmword_180169738+8, rdx
0x18003a072  jz      loc_180039F44
0x18003a078  jmp     loc_180039E8F
0x18003a07d  cmp     dword ptr cs:xmmword_180169738, 0
0x18003a084  mov     [rsp+1B8h+var_140], 0
0x18003a08c  mov     [rsp+1B8h+var_148], eax
0x18003a090  jz      short loc_18003A022
0x18003a092  mov     rdx, 4000000000000800h; unsigned __int64
0x18003a09c  test    qword ptr cs:xmmword_180169738+8, rdx
0x18003a0a3  jz      loc_18003A022
0x18003a0a9  jmp     loc_180039F64
0x18003a0ae  lea     rdx, String2; "."
0x18003a0b5  call    cs:__imp__wcsicmp
0x18003a0bb  test    eax, eax
0x18003a0bd  jz      loc_18003A162
0x18003a0c3  mov     ecx, [rsp+1B8h+nSize]
0x18003a0ca  xor     r8d, r8d; int
0x18003a0cd  mov     [rsp+1B8h+arg_10], rbp
0x18003a0d5  add     rcx, rcx; dwBytes
0x18003a0d8  mov     [rsp+1B8h+var_18], r14
0x18003a0e0  mov     edx, 1; int
0x18003a0e5  lea     r14, byte_180147320
0x18003a0ec  mov     r9, r14; char *
0x18003a0ef  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18003a0f4  mov     rbp, rax
0x18003a0f7  test    rax, rax
0x18003a0fa  jz      loc_18003A044
0x18003a100  lea     rdx, [rsp+1B8h+nSize]; nSize
0x18003a108  mov     [rsp+1B8h+arg_18], rsi
0x18003a110  mov     rcx, rax; lpBuffer
0x18003a113  call    cs:__imp_GetComputerNameW
0x18003a119  test    eax, eax
0x18003a11b  jz      short loc_18003A121
0x18003a11d  xor     esi, esi
0x18003a11f  jmp     short loc_18003A138
0x18003a121  call    cs:__imp_GetLastError
0x18003a127  mov     ecx, eax; unsigned int
0x18003a129  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18003a12e  mov     esi, eax
0x18003a130  test    eax, eax
0x18003a132  js      loc_18003A07D
0x18003a138  cmp     word ptr [rbx], 5Ch ; '\'
0x18003a13c  jnz     short loc_18003A148
0x18003a13e  add     rbx, 2
0x18003a142  cmp     word ptr [rbx], 5Ch ; '\'
0x18003a146  jz      short loc_18003A13E
0x18003a148  mov     rdx, rbx; String2
0x18003a14b  mov     rcx, rbp; String1
0x18003a14e  call    cs:__imp__wcsicmp
0x18003a154  xor     ecx, ecx
0x18003a156  test    eax, eax
0x18003a158  setz    cl
0x18003a15b  mov     [rdi], ecx
0x18003a15d  jmp     loc_18003A028
0x18003a162  mov     dword ptr [rdi], 1
0x18003a168  xor     eax, eax
0x18003a16a  jmp     loc_180039E75
```
