# SynthThread

- ea: `0x180010bb0`
- end: `0x180010cb2`
- name: `SynthThread`
- size: `258`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800104c0`
- `0x180010bb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010bf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010bf4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010c6f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010c6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010c21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010c21`

## pseudocode

```c
__int64 __fastcall SynthThread(char *lpThreadParameter)
{
  unsigned int i; // esi
  _QWORD *v3; // rax
  unsigned int v4; // ecx
  CDSLink *v5; // rbx
  DWORD v6; // edx
  __int64 result; // rax

  if ( *((_DWORD *)lpThreadParameter + 16) )
  {
    result = 0;
    *((_DWORD *)lpThreadParameter + 16) = 0;
  }
  else
  {
    do
    {
      for ( i = 0; i < *((_DWORD *)lpThreadParameter + 20); ++i )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 16));
        v3 = *(_QWORD **)lpThreadParameter;
        v4 = i;
        if ( *(_QWORD *)lpThreadParameter )
        {
          do
          {
            if ( !v4 )
              break;
            v3 = (_QWORD *)*v3;
            --v4;
          }
          while ( v3 );
        }
        v5 = (CDSLink *)(v3 - 2);
        if ( !v3 )
          v5 = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 16));
        if ( v5 && *((_DWORD *)v5 + 56) )
          CDSLink::SynthProc(v5);
      }
      v6 = *((_DWORD *)lpThreadParameter + 21);
      if ( v6 >= 2 )
      {
        if ( v6 > 0x64 )
        {
          *((_DWORD *)lpThreadParameter + 21) = 100;
          v6 = 100;
        }
      }
      else
      {
        *((_DWORD *)lpThreadParameter + 21) = 2;
        v6 = 2;
      }
      WaitForSingleObject(*((HANDLE *)lpThreadParameter + 9), v6);
    }
    while ( !*((_DWORD *)lpThreadParameter + 16) );
    result = 0;
    *((_DWORD *)lpThreadParameter + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180010bb0  mov     [rsp+arg_18], rdi
0x180010bb5  push    r14
0x180010bb7  sub     rsp, 20h
0x180010bbb  xor     r14d, r14d
0x180010bbe  mov     rdi, rcx
0x180010bc1  cmp     [rcx+40h], r14d
0x180010bc5  jnz     loc_180010CA0
0x180010bcb  mov     [rsp+28h+arg_0], rbx
0x180010bd0  mov     [rsp+28h+arg_8], rbp
0x180010bd5  mov     [rsp+28h+arg_10], rsi
0x180010bda  nop     word ptr [rax+rax+00h]
0x180010be0  mov     esi, r14d
0x180010be3  cmp     [rdi+50h], r14d
0x180010be7  jbe     short loc_180010C44
0x180010be9  nop     dword ptr [rax+00000000h]
0x180010bf0  lea     rcx, [rdi+10h]; lpCriticalSection
0x180010bf4  call    cs:__imp_EnterCriticalSection
0x180010bfa  mov     rax, [rdi]
0x180010bfd  mov     ecx, esi
0x180010bff  test    rax, rax
0x180010c02  jz      short loc_180010C12
0x180010c04  test    ecx, ecx
0x180010c06  jz      short loc_180010C12
0x180010c08  mov     rax, [rax]
0x180010c0b  dec     ecx
0x180010c0d  test    rax, rax
0x180010c10  jnz     short loc_180010C04
0x180010c12  test    rax, rax
0x180010c15  lea     rbx, [rax-10h]
0x180010c19  lea     rcx, [rdi+10h]; lpCriticalSection
0x180010c1d  cmovz   rbx, r14
0x180010c21  call    cs:__imp_LeaveCriticalSection
0x180010c27  test    rbx, rbx
0x180010c2a  jz      short loc_180010C3D
0x180010c2c  cmp     [rbx+0E0h], r14d
0x180010c33  jz      short loc_180010C3D
0x180010c35  mov     rcx, rbx; this
0x180010c38  call    ?SynthProc@CDSLink@@AEAAXXZ; CDSLink::SynthProc(void)
0x180010c3d  inc     esi
0x180010c3f  cmp     esi, [rdi+50h]
0x180010c42  jb      short loc_180010BF0
0x180010c44  mov     edx, [rdi+54h]
0x180010c47  cmp     edx, 2
0x180010c4a  jnb     short loc_180010C5A
0x180010c4c  mov     dword ptr [rdi+54h], 2
0x180010c53  mov     edx, 2
0x180010c58  jmp     short loc_180010C6B
0x180010c5a  cmp     edx, 64h ; 'd'
0x180010c5d  jbe     short loc_180010C6B
0x180010c5f  mov     dword ptr [rdi+54h], 64h ; 'd'
0x180010c66  mov     edx, 64h ; 'd'; dwMilliseconds
0x180010c6b  mov     rcx, [rdi+48h]; hHandle
0x180010c6f  call    cs:__imp_WaitForSingleObject
0x180010c75  cmp     [rdi+40h], r14d
0x180010c79  jz      loc_180010BE0
0x180010c7f  mov     rsi, [rsp+28h+arg_10]
0x180010c84  xor     eax, eax
0x180010c86  mov     rbp, [rsp+28h+arg_8]
0x180010c8b  mov     rbx, [rsp+28h+arg_0]
0x180010c90  mov     [rdi+40h], r14d
0x180010c94  mov     rdi, [rsp+28h+arg_18]
0x180010c99  add     rsp, 20h
0x180010c9d  pop     r14
0x180010c9f  retn
0x180010ca0  mov     rdi, [rsp+28h+arg_18]
0x180010ca5  xor     eax, eax
0x180010ca7  mov     [rcx+40h], r14d
0x180010cab  add     rsp, 20h
0x180010caf  pop     r14
0x180010cb1  retn
```
