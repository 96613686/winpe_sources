# CDRMCLock::Lock(ushort *)

- ea: `0x1800370d8`
- end: `0x180037213`
- name: `?Lock@CDRMCLock@@QEAAJPEAG@Z`
- size: `315`
- prototype: `int(CDRMCLock *__hidden this, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001ad10`
- `0x18001c610`
- `0x180034c24`
- `0x180035294`
- `0x1800355b4`
- `0x180036684`
- `0x180046d9c`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x1800370d8`
- `0x1800379a4`
- `0x18005bd72`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800371d7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800371d7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800371b6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800371b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371e1`

## pseudocode

```c
__int64 __fastcall CDRMCLock::Lock(CDRMCLock *this, unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rdi
  signed int v5; // ebx
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  unsigned __int16 **v9; // r8
  unsigned __int16 v10; // ax
  unsigned __int16 *v11; // rcx
  HANDLE MutexW; // rsi
  signed int LastError; // eax
  LPCWSTR lpName; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = v6 + 1;
    v8 = (unsigned __int16 *)operator new(saturated_mul(v6 + 1, 2u));
    v4 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, 2 * v7);
      v5 = StringCchCopyW(v4, v7, a2);
      if ( v5 >= 0 )
      {
        v10 = *v4;
        if ( *v4 )
        {
          v11 = v4;
          do
          {
            if ( v10 == 92 )
              v4[v11 - v4] = 47;
            v10 = *++v11;
          }
          while ( *v11 );
        }
        if ( !*(_QWORD *)this )
        {
          lpName = 0;
          MutexW = 0;
          if ( (int)DRMOS::AddPerUserPrefix((DRMOS *)v4, (const unsigned __int16 *)&lpName, v9) >= 0 )
            MutexW = CreateMutexW(0, 0, lpName);
          operator delete((void *)lpName);
          *(_QWORD *)this = MutexW;
          if ( !MutexW || WaitForSingleObject(MutexW, 0xFFFFFFFF) )
          {
            LastError = GetLastError();
            v5 = LastError;
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
    else
    {
      v5 = -2147024882;
    }
  }
  else
  {
    v4 = 0;
    v5 = -2147024809;
  }
  operator delete(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800370d8  mov     [rsp+arg_0], rbx
0x1800370dd  mov     [rsp+arg_10], rbp
0x1800370e2  push    rsi
0x1800370e3  push    rdi
0x1800370e4  push    r14
0x1800370e6  sub     rsp, 20h
0x1800370ea  xor     ebp, ebp
0x1800370ec  mov     rbx, rdx
0x1800370ef  mov     r14, rcx
0x1800370f2  test    rdx, rdx
0x1800370f5  jnz     short loc_180037103
0x1800370f7  mov     edi, ebp
0x1800370f9  mov     ebx, 80070057h
0x1800370fe  jmp     loc_1800371F6
0x180037103  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180037107  mov     rax, rcx
0x18003710a  inc     rax
0x18003710d  cmp     [rdx+rax*2], bp
0x180037111  jnz     short loc_18003710A
0x180037113  lea     rsi, [rax+1]
0x180037117  mov     eax, 2
0x18003711c  mul     rsi
0x18003711f  cmovb   rax, rcx
0x180037123  mov     rcx, rax; Size
0x180037126  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003712b  mov     rdi, rax
0x18003712e  test    rax, rax
0x180037131  jnz     short loc_18003713D
0x180037133  mov     ebx, 8007000Eh
0x180037138  jmp     loc_1800371F6
0x18003713d  lea     r8, [rsi+rsi]; Size
0x180037141  xor     edx, edx; Val
0x180037143  mov     rcx, rdi; void *
0x180037146  call    memset_0
0x18003714b  mov     r8, rbx; unsigned __int16 *
0x18003714e  mov     rdx, rsi; unsigned __int64
0x180037151  mov     rcx, rdi; unsigned __int16 *
0x180037154  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037159  mov     ebx, eax
0x18003715b  test    eax, eax
0x18003715d  js      loc_1800371F6
0x180037163  movzx   eax, word ptr [rdi]
0x180037166  test    ax, ax
0x180037169  jz      short loc_18003718F
0x18003716b  mov     rcx, rdi
0x18003716e  cmp     ax, 5Ch ; '\'
0x180037172  jnz     short loc_180037183
0x180037174  mov     rax, rcx
0x180037177  sub     rax, rdi
0x18003717a  sar     rax, 1
0x18003717d  mov     word ptr [rdi+rax*2], 2Fh ; '/'
0x180037183  add     rcx, 2
0x180037187  movzx   eax, word ptr [rcx]
0x18003718a  test    ax, ax
0x18003718d  jnz     short loc_18003716E
0x18003718f  cmp     [r14], rbp
0x180037192  jnz     short loc_1800371F6
0x180037194  lea     rdx, [rsp+38h+lpName]; unsigned __int16 *
0x180037199  mov     [rsp+38h+lpName], rbp
0x18003719e  mov     rcx, rdi; this
0x1800371a1  mov     rsi, rbp
0x1800371a4  call    ?AddPerUserPrefix@DRMOS@@YAJPEBGPEAPEAG@Z; DRMOS::AddPerUserPrefix(ushort const *,ushort * *)
0x1800371a9  test    eax, eax
0x1800371ab  js      short loc_1800371BF
0x1800371ad  mov     r8, [rsp+38h+lpName]; lpName
0x1800371b2  xor     edx, edx; bInitialOwner
0x1800371b4  xor     ecx, ecx; lpMutexAttributes
0x1800371b6  call    cs:__imp_CreateMutexW
0x1800371bc  mov     rsi, rax
0x1800371bf  mov     rcx, [rsp+38h+lpName]; Block
0x1800371c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800371c9  mov     [r14], rsi
0x1800371cc  test    rsi, rsi
0x1800371cf  jz      short loc_1800371E1
0x1800371d1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800371d4  mov     rcx, rsi; hHandle
0x1800371d7  call    cs:__imp_WaitForSingleObject
0x1800371dd  test    eax, eax
0x1800371df  jz      short loc_1800371F6
0x1800371e1  call    cs:__imp_GetLastError
0x1800371e7  mov     ebx, eax
0x1800371e9  test    eax, eax
0x1800371eb  jle     short loc_1800371F6
0x1800371ed  movzx   ebx, ax
0x1800371f0  or      ebx, 80070000h
0x1800371f6  mov     rcx, rdi; Block
0x1800371f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800371fe  mov     rbp, [rsp+38h+arg_10]
0x180037203  mov     eax, ebx
0x180037205  mov     rbx, [rsp+38h+arg_0]
0x18003720a  add     rsp, 20h
0x18003720e  pop     r14
0x180037210  pop     rdi
0x180037211  pop     rsi
0x180037212  retn
```
