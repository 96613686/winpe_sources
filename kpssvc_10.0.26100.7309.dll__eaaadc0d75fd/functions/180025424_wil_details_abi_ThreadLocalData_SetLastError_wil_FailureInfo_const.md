# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180025424`
- end: `0x180025520`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `252`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d820`

## callees

- `0x180023520`
- `0x180025090`
- `0x180025424`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  _DWORD *v7; // r8
  _DWORD *v8; // rcx
  _DWORD *v9; // rdx
  unsigned __int16 v10; // dx

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
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
  v7 = (_DWORD *)*((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v2 || (v8 = &v7[20 * *((unsigned __int16 *)this + 16)], v7 == v8) )
    {
LABEL_14:
      v10 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v10;
      wil::details_abi::ThreadLocalFailureInfo::Set(
        (wil::details_abi::ThreadLocalFailureInfo *)&v7[20 * v10],
        a2,
        _InterlockedIncrement(*((volatile signed __int32 **)this + 1)));
    }
    else
    {
      v9 = v7 + 2;
      while ( *(v9 - 1) <= *((_DWORD *)this + 4) || *v9 != *((_DWORD *)a2 + 2) )
      {
        v9 += 20;
        if ( v9 - 2 == v8 )
          goto LABEL_14;
      }
    }
  }
}

```

## disassembly

```asm
0x180025424  mov     rax, rsp
0x180025427  mov     [rax+8], rbx
0x18002542b  mov     [rax+10h], rbp
0x18002542f  mov     [rax+18h], rsi
0x180025433  mov     [rax+20h], rdi
0x180025437  push    r14
0x180025439  sub     rsp, 20h
0x18002543d  mov     edi, [rcx+10h]
0x180025440  xor     ebp, ebp
0x180025442  mov     rsi, rdx
0x180025445  mov     rbx, rcx
0x180025448  lea     r14d, [rbp+50h]
0x18002544c  cmp     [rcx+18h], rbp
0x180025450  jnz     short loc_180025488
0x180025452  test    edi, edi
0x180025454  jz      short loc_180025488
0x180025456  mov     edx, 190h; dwBytes
0x18002545b  lea     ecx, [rbp+8]; dwFlags
0x18002545e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180025463  mov     [rbx+18h], rax
0x180025467  test    rax, rax
0x18002546a  jz      short loc_180025488
0x18002546c  mov     dword ptr [rbx+20h], 5
0x180025473  lea     rcx, [rax+190h]
0x18002547a  jmp     short loc_180025483
0x18002547c  mov     [rax], r14w
0x180025480  add     rax, r14
0x180025483  cmp     rax, rcx
0x180025486  jnz     short loc_18002547C
0x180025488  mov     r8, [rbx+18h]
0x18002548c  test    r8, r8
0x18002548f  jz      short loc_180025504
0x180025491  test    edi, edi
0x180025493  jz      short loc_1800254CA
0x180025495  movzx   eax, word ptr [rbx+20h]
0x180025499  lea     rcx, [rax+rax*4]
0x18002549d  shl     rcx, 4
0x1800254a1  add     rcx, r8
0x1800254a4  cmp     r8, rcx
0x1800254a7  jz      short loc_1800254CA
0x1800254a9  mov     r9d, [rbx+10h]
0x1800254ad  lea     rdx, [r8+8]
0x1800254b1  cmp     [rdx-4], r9d
0x1800254b5  jbe     short loc_1800254BE
0x1800254b7  mov     eax, [rsi+8]
0x1800254ba  cmp     [rdx], eax
0x1800254bc  jz      short loc_180025504
0x1800254be  add     rdx, r14
0x1800254c1  lea     rax, [rdx-8]
0x1800254c5  cmp     rax, rcx
0x1800254c8  jnz     short loc_1800254B1
0x1800254ca  movzx   eax, word ptr [rbx+22h]
0x1800254ce  xor     edx, edx
0x1800254d0  movzx   ecx, word ptr [rbx+20h]
0x1800254d4  inc     eax
0x1800254d6  div     ecx
0x1800254d8  movzx   eax, dx
0x1800254db  mov     [rbx+22h], dx
0x1800254df  lea     rcx, [rax+rax*4]
0x1800254e3  mov     rax, [rbx+8]
0x1800254e7  shl     rcx, 4
0x1800254eb  add     rcx, r8; this
0x1800254ee  mov     r8d, 1
0x1800254f4  lock xadd [rax], r8d
0x1800254f9  inc     r8d; unsigned int
0x1800254fc  mov     rdx, rsi; struct wil::FailureInfo *
0x1800254ff  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180025504  mov     rbx, [rsp+28h+arg_0]
0x180025509  mov     rbp, [rsp+28h+arg_8]
0x18002550e  mov     rsi, [rsp+28h+arg_10]
0x180025513  mov     rdi, [rsp+28h+arg_18]
0x180025518  add     rsp, 20h
0x18002551c  pop     r14
0x18002551e  retn
```
