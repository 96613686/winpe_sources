# WriteEventEx

- ea: `0x1800a3218`
- end: `0x1800a32d0`
- name: `WriteEventEx`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006f910`

## callees

- `0x180026e94`
- `0x1800a3218`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800a32ab`
- `ntdll!EtwEventWrite` at `0x1800a32ab`
- `ntdll!EtwEventEnabled` at `0x1800a3241`
- `ntdll!EtwEventEnabled` at `0x1800a3241`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a32bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a32bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a3258`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a3258`

## pseudocode

```c
__int64 __fastcall WriteEventEx(_OWORD *a1, __int64 a2, const wchar_t **a3)
{
  unsigned int v5; // edi
  _QWORD *v6; // rbx
  const wchar_t *v7; // rdi
  unsigned int v8; // eax
  unsigned __int64 v10[5]; // [rsp+20h] [rbp-28h] BYREF

  *(_OWORD *)v10 = *a1;
  v5 = 0;
  if ( (unsigned __int8)EtwEventEnabled(handle, v10) )
  {
    v6 = 0;
    if ( a3 )
    {
      v6 = LocalAlloc(0x40u, 0x10u);
      if ( v6 )
      {
        v10[0] = 0;
        v7 = *a3;
        if ( (int)StringCbLengthW(*a3, 0xFFFFFFFE, v10) >= 0 )
        {
          v8 = LODWORD(v10[0]) + 2;
          *v6 = v7;
          v6[1] = v8;
        }
      }
    }
    v5 = EtwEventWrite(handle, a1, 1, v6);
    if ( v6 )
      LocalFree(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x1800a3218  mov     [rsp+arg_8], rbx
0x1800a321d  push    rbp
0x1800a321e  push    rsi
0x1800a321f  push    rdi
0x1800a3220  sub     rsp, 30h
0x1800a3224  movaps  xmm0, xmmword ptr [rcx]
0x1800a3227  lea     rdx, [rsp+48h+var_28]
0x1800a322c  mov     rbp, rcx
0x1800a322f  movdqa  xmmword ptr [rsp+48h+var_28], xmm0
0x1800a3235  mov     rcx, cs:?handle@@3_KA; unsigned __int64 handle
0x1800a323c  mov     rsi, r8
0x1800a323f  xor     edi, edi
0x1800a3241  call    cs:__imp_EtwEventEnabled
0x1800a3247  test    al, al
0x1800a3249  jz      short loc_1800A32C1
0x1800a324b  xor     ebx, ebx
0x1800a324d  test    rsi, rsi
0x1800a3250  jz      short loc_1800A3298
0x1800a3252  lea     edx, [rdi+10h]; uBytes
0x1800a3255  lea     ecx, [rdi+40h]; uFlags
0x1800a3258  call    cs:__imp_LocalAlloc
0x1800a325e  mov     rbx, rax
0x1800a3261  test    rax, rax
0x1800a3264  jz      short loc_1800A3298
0x1800a3266  mov     [rsp+48h+var_28], rdi
0x1800a326b  lea     r8, [rsp+48h+var_28]; unsigned __int64 *
0x1800a3270  mov     rdi, [rsi]
0x1800a3273  mov     edx, 0FFFFFFFEh; unsigned __int64
0x1800a3278  mov     rcx, rdi; wchar_t *
0x1800a327b  call    ?StringCbLengthW@@YAJPEB_W_KPEA_K@Z; StringCbLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1800a3280  test    eax, eax
0x1800a3282  js      short loc_1800A3298
0x1800a3284  mov     eax, dword ptr [rsp+48h+var_28]
0x1800a3288  add     eax, 2
0x1800a328b  mov     [rbx], rdi
0x1800a328e  mov     [rbx+8], eax
0x1800a3291  mov     dword ptr [rbx+0Ch], 0
0x1800a3298  mov     rcx, cs:?handle@@3_KA; unsigned __int64 handle
0x1800a329f  mov     r9, rbx
0x1800a32a2  mov     r8d, 1
0x1800a32a8  mov     rdx, rbp
0x1800a32ab  call    cs:__imp_EtwEventWrite
0x1800a32b1  mov     edi, eax
0x1800a32b3  test    rbx, rbx
0x1800a32b6  jz      short loc_1800A32C1
0x1800a32b8  mov     rcx, rbx; hMem
0x1800a32bb  call    cs:__imp_LocalFree
0x1800a32c1  mov     rbx, [rsp+48h+arg_8]
0x1800a32c6  mov     eax, edi
0x1800a32c8  add     rsp, 30h
0x1800a32cc  pop     rdi
0x1800a32cd  pop     rsi
0x1800a32ce  pop     rbp
0x1800a32cf  retn
```
