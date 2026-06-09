# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140005e4c`
- end: `0x140005f1b`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400046e0`

## callees

- `0x1400056d8`
- `0x140005ab4`
- `0x140005e4c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v3; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // r9
  __int64 i; // rcx
  unsigned __int16 v9; // dx
  volatile signed __int32 *v10; // rax

  v3 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v3 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( v3 )
    {
      for ( i = *((_QWORD *)this + 3); i != v7 + 80LL * *((unsigned __int16 *)this + 16); i += 80 )
      {
        if ( *(_DWORD *)(i + 4) > *((_DWORD *)this + 4) && *(_DWORD *)(i + 8) == *((_DWORD *)a2 + 2) )
          return;
      }
    }
    v9 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
    v10 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    *((_WORD *)this + 17) = v9;
    wil::details_abi::ThreadLocalFailureInfo::Set(
      (wil::details_abi::ThreadLocalFailureInfo *)(v7 + 80LL * v9),
      a2,
      _InterlockedIncrement(v10));
  }
}

```

## disassembly

```asm
0x140005e4c  push    rbx
0x140005e4e  push    rbp
0x140005e4f  push    rsi
0x140005e50  push    rdi
0x140005e51  sub     rsp, 28h
0x140005e55  cmp     qword ptr [rcx+18h], 0
0x140005e5a  mov     rsi, rdx
0x140005e5d  mov     edi, [rcx+10h]
0x140005e60  mov     rbx, rcx
0x140005e63  mov     ebp, 50h ; 'P'
0x140005e68  jnz     short loc_140005E9F
0x140005e6a  test    edi, edi
0x140005e6c  jz      short loc_140005E9F
0x140005e6e  mov     edx, 190h; dwBytes
0x140005e73  lea     ecx, [rbp-48h]; dwFlags
0x140005e76  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005e7b  mov     [rbx+18h], rax
0x140005e7f  test    rax, rax
0x140005e82  jz      short loc_140005E9F
0x140005e84  mov     dword ptr [rbx+20h], 5
0x140005e8b  lea     rcx, [rax+190h]
0x140005e92  jmp     short loc_140005E9A
0x140005e94  mov     [rax], bp
0x140005e97  add     rax, rbp
0x140005e9a  cmp     rax, rcx
0x140005e9d  jnz     short loc_140005E94
0x140005e9f  mov     r9, [rbx+18h]
0x140005ea3  test    r9, r9
0x140005ea6  jz      short loc_140005F12
0x140005ea8  test    edi, edi
0x140005eaa  jz      short loc_140005ED8
0x140005eac  movzx   eax, word ptr [rbx+20h]
0x140005eb0  mov     rcx, r9
0x140005eb3  lea     rdx, [rax+rax*4]
0x140005eb7  shl     rdx, 4
0x140005ebb  add     rdx, r9
0x140005ebe  cmp     rcx, rdx
0x140005ec1  jz      short loc_140005ED8
0x140005ec3  mov     eax, [rbx+10h]
0x140005ec6  cmp     [rcx+4], eax
0x140005ec9  jbe     short loc_140005ED3
0x140005ecb  mov     eax, [rsi+8]
0x140005ece  cmp     [rcx+8], eax
0x140005ed1  jz      short loc_140005F12
0x140005ed3  add     rcx, rbp
0x140005ed6  jmp     short loc_140005EBE
0x140005ed8  movzx   eax, word ptr [rbx+22h]
0x140005edc  xor     edx, edx
0x140005ede  movzx   ecx, word ptr [rbx+20h]
0x140005ee2  inc     eax
0x140005ee4  div     ecx
0x140005ee6  mov     rax, [rbx+8]
0x140005eea  mov     r8d, 1
0x140005ef0  mov     [rbx+22h], dx
0x140005ef4  lock xadd [rax], r8d
0x140005ef9  movzx   eax, dx
0x140005efc  inc     r8d; unsigned int
0x140005eff  mov     rdx, rsi; struct wil::FailureInfo *
0x140005f02  lea     rcx, [rax+rax*4]
0x140005f06  shl     rcx, 4
0x140005f0a  add     rcx, r9; this
0x140005f0d  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140005f12  add     rsp, 28h
0x140005f16  pop     rdi
0x140005f17  pop     rsi
0x140005f18  pop     rbp
0x140005f19  pop     rbx
0x140005f1a  retn
```
