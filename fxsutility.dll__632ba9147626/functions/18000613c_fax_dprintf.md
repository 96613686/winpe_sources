# fax_dprintf

- ea: `0x18000613c`
- end: `0x180006268`
- name: `fax_dprintf`
- size: `300`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006270`
- `0x18000d94c`
- `0x18000da1c`

## callees

- `0x180001d98`
- `0x180005f68`
- `0x18000613c`
- `0x180015cbe`
- `0x180015cf0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800061d2`
- `msvcrt!_vsnwprintf` at `0x1800061d2`
- `KERNEL32!OutputDebugStringW` at `0x180006242`
- `KERNEL32!OutputDebugStringW` at `0x180006242`

## pseudocode

```c
void fax_dprintf(const wchar_t *a1, ...)
{
  const wchar_t *v1; // rbx
  int DebugLevel; // eax
  unsigned int v3; // eax
  unsigned __int64 v4; // rax
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  wchar_t Buffer[1024]; // [rsp+38h] [rbp-D0h] BYREF
  va_list Args; // [rsp+870h] [rbp+768h] BYREF

  va_start(Args, a1);
  v1 = a1;
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( dword_18001EC68 )
  {
    DebugLevel = dword_18001E4E0;
  }
  else
  {
    DebugLevel = GetDebugLevel();
    v1 = a1;
    dword_18001E4E0 = DebugLevel;
    dword_18001EC68 = 1;
  }
  if ( DebugLevel > 0 )
  {
    v3 = _vsnwprintf(Buffer, 0x3FFu, v1, Args);
    if ( v3 < 0x400 )
    {
      if ( v3 == 1023 )
        Buffer[1023] = 0;
      v4 = -1;
      do
        ++v4;
      while ( Buffer[v4] );
      v5 = 1021;
      if ( v4 < 0x3FD )
        v5 = (unsigned int)v4;
      if ( Buffer[(unsigned int)(v5 - 1)] != 10 )
      {
        Buffer[v5] = 13;
        Buffer[(unsigned int)(v5 + 1)] = 10;
        v6 = 2LL * (unsigned int)(v5 + 2);
        if ( v6 >= 0x800 )
          _report_rangecheckfailure(v6, v5, 10);
        Buffer[(unsigned int)(v5 + 2)] = 0;
      }
      OutputDebugStringW(Buffer);
    }
  }
}

```

## disassembly

```asm
0x18000613c  mov     rax, rsp
0x18000613f  mov     [rax+8], rcx
0x180006143  mov     [rax+10h], rdx
0x180006147  mov     [rax+18h], r8
0x18000614b  mov     [rax+20h], r9
0x18000614f  push    rbp
0x180006150  push    rbx
0x180006151  push    rdi
0x180006152  lea     rbp, [rax-758h]
0x180006159  sub     rsp, 840h
0x180006160  mov     rax, cs:__security_cookie
0x180006167  xor     rax, rsp
0x18000616a  mov     [rbp+750h+var_20], rax
0x180006171  mov     rbx, rcx
0x180006174  xor     edx, edx; Val
0x180006176  lea     rcx, [rsp+850h+Buffer]; void *
0x18000617b  mov     r8d, 800h; Size
0x180006181  call    memset_0
0x180006186  xor     edi, edi
0x180006188  cmp     cs:dword_18001EC68, edi
0x18000618e  jnz     short loc_1800061AE
0x180006190  call    ?GetDebugLevel@@YAKXZ; GetDebugLevel(void)
0x180006195  mov     rbx, [rbp+750h+Format]
0x18000619c  mov     cs:dword_18001E4E0, eax
0x1800061a2  mov     cs:dword_18001EC68, 1
0x1800061ac  jmp     short loc_1800061B4
0x1800061ae  mov     eax, cs:dword_18001E4E0
0x1800061b4  test    eax, eax
0x1800061b6  jle     loc_180006248
0x1800061bc  mov     r8, rbx; Format
0x1800061bf  lea     r9, [rbp+750h+Args]; Args
0x1800061c6  mov     ebx, 3FFh
0x1800061cb  lea     rcx, [rsp+850h+Buffer]; Buffer
0x1800061d0  mov     edx, ebx; BufferCount
0x1800061d2  call    cs:__imp__vsnwprintf
0x1800061d8  test    eax, eax
0x1800061da  js      short loc_180006248
0x1800061dc  cmp     eax, ebx
0x1800061de  ja      short loc_180006248
0x1800061e0  jnz     short loc_1800061E9
0x1800061e2  mov     [rbp+750h+var_22], di
0x1800061e9  lea     rcx, [rsp+850h+Buffer]
0x1800061ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800061f2  inc     rax
0x1800061f5  cmp     [rcx+rax*2], di
0x1800061f9  jnz     short loc_1800061F2
0x1800061fb  mov     edx, 3FDh
0x180006200  mov     r8d, 0Ah
0x180006206  cmp     rax, rdx
0x180006209  cmovb   edx, eax
0x18000620c  lea     eax, [rdx-1]
0x18000620f  cmp     [rsp+rax*2+850h+Buffer], r8w
0x180006215  jz      short loc_18000623D
0x180006217  lea     ecx, [r8+3]
0x18000621b  mov     [rsp+rdx*2+850h+Buffer], cx
0x180006220  lea     eax, [rdx+1]
0x180006223  lea     ecx, [rdx+2]
0x180006226  mov     [rsp+rax*2+850h+Buffer], r8w
0x18000622c  add     rcx, rcx
0x18000622f  cmp     rcx, 800h
0x180006236  jnb     short loc_180006262
0x180006238  mov     [rsp+rcx+850h+Buffer], di
0x18000623d  lea     rcx, [rsp+850h+Buffer]; lpOutputString
0x180006242  call    cs:__imp_OutputDebugStringW
0x180006248  mov     rcx, [rbp+750h+var_20]
0x18000624f  xor     rcx, rsp; StackCookie
0x180006252  call    __security_check_cookie
0x180006257  add     rsp, 840h
0x18000625e  pop     rdi
0x18000625f  pop     rbx
0x180006260  pop     rbp
0x180006261  retn
0x180006262  call    __report_rangecheckfailure
```
