# CreatePnpxDafContext(_PNPX_DAF_CONTEXT * *)

- ea: `0x18000f6cc`
- end: `0x18000f73f`
- name: `?CreatePnpxDafContext@@YAJPEAPEAU_PNPX_DAF_CONTEXT@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(struct _PNPX_DAF_CONTEXT **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f748`
- `0x18000f858`
- `0x18000f95c`

## callees

- `0x1800019d4`
- `0x18000f6cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f71d`
- `KERNEL32!GetLastError` at `0x18000f71d`
- `KERNEL32!CreateEventW` at `0x18000f709`
- `KERNEL32!CreateEventW` at `0x18000f709`

## pseudocode

```c
__int64 __fastcall CreatePnpxDafContext(struct _PNPX_DAF_CONTEXT **a1)
{
  struct _PNPX_DAF_CONTEXT *v2; // rax
  unsigned int v3; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax

  v2 = (struct _PNPX_DAF_CONTEXT *)operator new(0x20u);
  *a1 = v2;
  if ( v2 )
  {
    v3 = 0;
    *(_OWORD *)v2 = 0;
    *((_OWORD *)v2 + 1) = 0;
    EventW = CreateEventW(0, 1, 0, 0);
    *(_QWORD *)*a1 = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x18000f6cc  mov     [rsp+arg_0], rbx
0x18000f6d1  push    rdi
0x18000f6d2  sub     rsp, 20h
0x18000f6d6  mov     rdi, rcx
0x18000f6d9  mov     ecx, 20h ; ' '; Size
0x18000f6de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f6e3  mov     [rdi], rax
0x18000f6e6  test    rax, rax
0x18000f6e9  jnz     short loc_18000F6F2
0x18000f6eb  mov     ebx, 8007000Eh
0x18000f6f0  jmp     short loc_18000F732
0x18000f6f2  xorps   xmm0, xmm0
0x18000f6f5  xor     ebx, ebx
0x18000f6f7  movups  xmmword ptr [rax], xmm0
0x18000f6fa  xor     r9d, r9d; lpName
0x18000f6fd  xor     r8d, r8d; bInitialState
0x18000f700  xor     ecx, ecx; lpEventAttributes
0x18000f702  lea     edx, [rbx+1]; bManualReset
0x18000f705  movups  xmmword ptr [rax+10h], xmm0
0x18000f709  call    cs:__imp_CreateEventW
0x18000f70f  mov     rcx, rax
0x18000f712  mov     rax, [rdi]
0x18000f715  mov     [rax], rcx
0x18000f718  test    rcx, rcx
0x18000f71b  jnz     short loc_18000F732
0x18000f71d  call    cs:__imp_GetLastError
0x18000f723  mov     ebx, eax
0x18000f725  test    eax, eax
0x18000f727  jle     short loc_18000F732
0x18000f729  movzx   ebx, ax
0x18000f72c  or      ebx, 80070000h
0x18000f732  mov     eax, ebx
0x18000f734  mov     rbx, [rsp+28h+arg_0]
0x18000f739  add     rsp, 20h
0x18000f73d  pop     rdi
0x18000f73e  retn
```
