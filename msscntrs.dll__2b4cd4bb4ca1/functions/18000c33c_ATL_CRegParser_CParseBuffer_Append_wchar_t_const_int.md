# ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)

- ea: `0x18000c33c`
- end: `0x18000c3f2`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z`
- size: `182`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e624`

## callees

- `0x18000c33c`
- `0x180010cbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000c38f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000c38f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const wchar_t *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  int v10; // ecx
  unsigned __int64 v12; // [rsp+20h] [rbp-28h]

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 < v7 )
    {
LABEL_9:
      if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
      {
        v10 = v7 - *(_DWORD *)this;
        if ( v10 <= v7 )
        {
          ATL::Checked::memcpy_s(
            (ATL::Checked *)(*((_QWORD *)this + 1) + 2LL * *(int *)this),
            (void *)(2LL * v10),
            (unsigned __int64)a2,
            (const void *)(2 * a3),
            v12);
          *(_DWORD *)this += a3;
          *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
          return 1;
        }
      }
    }
    else
    {
      while ( v7 <= 0x3FFFFFFF )
      {
        v7 *= 2;
        if ( v6 < v7 )
        {
          v8 = 2LL * (unsigned int)v7;
          if ( v8 <= 0xFFFFFFFF )
          {
            v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
            if ( v9 )
            {
              *((_QWORD *)this + 1) = v9;
              *((_DWORD *)this + 1) = v7;
              goto LABEL_9;
            }
          }
          return 0;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c33c  push    rbx
0x18000c33e  push    rbp
0x18000c33f  push    rsi
0x18000c340  push    rdi
0x18000c341  sub     rsp, 28h
0x18000c345  mov     rdi, rcx
0x18000c348  mov     esi, r8d
0x18000c34b  lea     ecx, [r8+1]
0x18000c34f  mov     rbp, rdx
0x18000c352  add     ecx, [rdi]
0x18000c354  cmp     ecx, [rdi]
0x18000c356  jle     loc_18000C3E7
0x18000c35c  cmp     ecx, r8d
0x18000c35f  jle     loc_18000C3E7
0x18000c365  mov     ebx, [rdi+4]
0x18000c368  cmp     ecx, ebx
0x18000c36a  jl      short loc_18000C3A1
0x18000c36c  cmp     ebx, 3FFFFFFFh
0x18000c372  jg      short loc_18000C3E7
0x18000c374  add     ebx, ebx
0x18000c376  cmp     ecx, ebx
0x18000c378  jge     short loc_18000C36C
0x18000c37a  mov     eax, ebx
0x18000c37c  mov     ecx, 0FFFFFFFFh
0x18000c381  add     rax, rax
0x18000c384  cmp     rax, rcx
0x18000c387  ja      short loc_18000C3E7
0x18000c389  mov     rcx, [rdi+8]; pv
0x18000c38d  mov     edx, eax; cb
0x18000c38f  call    cs:__imp_CoTaskMemRealloc
0x18000c395  test    rax, rax
0x18000c398  jz      short loc_18000C3E7
0x18000c39a  mov     [rdi+8], rax
0x18000c39e  mov     [rdi+4], ebx
0x18000c3a1  cmp     dword ptr [rdi], 0
0x18000c3a4  jl      short loc_18000C3E7
0x18000c3a6  cmp     [rdi], ebx
0x18000c3a8  jge     short loc_18000C3E7
0x18000c3aa  mov     ecx, ebx
0x18000c3ac  sub     ecx, [rdi]
0x18000c3ae  cmp     ecx, ebx
0x18000c3b0  jg      short loc_18000C3E7
0x18000c3b2  movsxd  rdx, ecx
0x18000c3b5  lea     eax, [rsi+rsi]
0x18000c3b8  movsxd  rcx, dword ptr [rdi]
0x18000c3bb  add     rdx, rdx; void *
0x18000c3be  movsxd  r9, eax; void *
0x18000c3c1  mov     r8, rbp; unsigned __int64
0x18000c3c4  mov     rax, [rdi+8]
0x18000c3c8  lea     rcx, [rax+rcx*2]; this
0x18000c3cc  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18000c3d1  add     [rdi], esi
0x18000c3d3  movsxd  rdx, dword ptr [rdi]
0x18000c3d6  xor     eax, eax
0x18000c3d8  mov     rcx, [rdi+8]
0x18000c3dc  mov     [rcx+rdx*2], ax
0x18000c3e0  mov     eax, 1
0x18000c3e5  jmp     short loc_18000C3E9
0x18000c3e7  xor     eax, eax
0x18000c3e9  add     rsp, 28h
0x18000c3ed  pop     rdi
0x18000c3ee  pop     rsi
0x18000c3ef  pop     rbp
0x18000c3f0  pop     rbx
0x18000c3f1  retn
```
