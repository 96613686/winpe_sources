# Dfdll::CBufferBase::Reverse(uint,uint)

- ea: `0x180003c80`
- end: `0x180003d4b`
- name: `?Reverse@CBufferBase@Dfdll@@UEAAJII@Z`
- size: `203`
- prototype: `__int64 __fastcall(Dfdll::CBufferBase *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003c80`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CBufferBase::Reverse(Dfdll::CBufferBase *this, unsigned int a2, unsigned int a3)
{
  unsigned int v3; // ebx
  unsigned int v4; // edi
  __int64 result; // rax
  unsigned int v7; // eax
  __int64 v8; // rbp
  _BYTE *v9; // rcx
  __int64 v10; // r8
  char *v11; // rdx
  char v12; // al
  char *v13; // [rsp+20h] [rbp-18h] BYREF
  _BYTE *v14; // [rsp+58h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  if ( a2 > a3 || a3 >= *((_DWORD *)this + 4) )
    return 2147942487LL;
  v7 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *))(*(_QWORD *)this + 72LL))(this);
  v14 = 0;
  v13 = 0;
  v8 = v7;
  while ( v4 < v3 )
  {
    result = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *, _QWORD, _BYTE **))(*(_QWORD *)this + 64LL))(
               this,
               v4,
               &v14);
    if ( (int)result < 0 )
      return result;
    result = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *, _QWORD, char **))(*(_QWORD *)this + 64LL))(this, v3, &v13);
    if ( (int)result < 0 )
      return result;
    if ( (_DWORD)v8 )
    {
      v9 = v14;
      v10 = v8;
      v11 = v13;
      do
      {
        *v9 ^= *v11;
        *v11 ^= *v9;
        v12 = *v11++;
        *v9++ ^= v12;
        --v10;
      }
      while ( v10 );
    }
    ++v4;
    --v3;
  }
  return 0;
}

```

## disassembly

```asm
0x180003c80  mov     [rsp+arg_0], rbx
0x180003c85  mov     [rsp+arg_8], rbp
0x180003c8a  mov     [rsp+arg_10], rsi
0x180003c8f  push    rdi
0x180003c90  sub     rsp, 30h
0x180003c94  mov     ebx, r8d
0x180003c97  mov     edi, edx
0x180003c99  mov     rsi, rcx
0x180003c9c  cmp     edx, r8d
0x180003c9f  jbe     short loc_180003CAB
0x180003ca1  mov     eax, 80070057h
0x180003ca6  jmp     loc_180003D36
0x180003cab  cmp     ebx, [rcx+10h]
0x180003cae  jnb     short loc_180003CA1
0x180003cb0  mov     rax, [rcx]
0x180003cb3  mov     rax, [rax+48h]
0x180003cb7  call    cs:__guard_dispatch_icall_fptr
0x180003cbd  and     [rsp+38h+arg_18], 0
0x180003cc3  and     [rsp+38h+var_18], 0
0x180003cc9  mov     ebp, eax
0x180003ccb  jmp     short loc_180003D30
0x180003ccd  mov     rax, [rsi]
0x180003cd0  lea     r8, [rsp+38h+arg_18]
0x180003cd5  mov     edx, edi
0x180003cd7  mov     rcx, rsi
0x180003cda  mov     rax, [rax+40h]
0x180003cde  call    cs:__guard_dispatch_icall_fptr
0x180003ce4  test    eax, eax
0x180003ce6  js      short loc_180003D36
0x180003ce8  mov     rax, [rsi]
0x180003ceb  lea     r8, [rsp+38h+var_18]
0x180003cf0  mov     edx, ebx
0x180003cf2  mov     rcx, rsi
0x180003cf5  mov     rax, [rax+40h]
0x180003cf9  call    cs:__guard_dispatch_icall_fptr
0x180003cff  test    eax, eax
0x180003d01  js      short loc_180003D36
0x180003d03  test    ebp, ebp
0x180003d05  jz      short loc_180003D2C
0x180003d07  mov     rcx, [rsp+38h+arg_18]
0x180003d0c  mov     r8, rbp
0x180003d0f  mov     rdx, [rsp+38h+var_18]
0x180003d14  mov     al, [rdx]
0x180003d16  xor     [rcx], al
0x180003d18  mov     al, [rcx]
0x180003d1a  xor     [rdx], al
0x180003d1c  mov     al, [rdx]
0x180003d1e  inc     rdx
0x180003d21  xor     [rcx], al
0x180003d23  inc     rcx
0x180003d26  sub     r8, 1
0x180003d2a  jnz     short loc_180003D14
0x180003d2c  inc     edi
0x180003d2e  dec     ebx
0x180003d30  cmp     edi, ebx
0x180003d32  jb      short loc_180003CCD
0x180003d34  xor     eax, eax
0x180003d36  mov     rbx, [rsp+38h+arg_0]
0x180003d3b  mov     rbp, [rsp+38h+arg_8]
0x180003d40  mov     rsi, [rsp+38h+arg_10]
0x180003d45  add     rsp, 30h
0x180003d49  pop     rdi
0x180003d4a  retn
```
