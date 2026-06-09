# PushMessage::GetHeaderValue(ushort const *,ushort * *)

- ea: `0x180019ce4`
- end: `0x180019d85`
- name: `?GetHeaderValue@PushMessage@@QEAAJPEBGPEAPEAG@Z`
- size: `161`
- prototype: `__int64 __fastcall(PushMessage *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016110`

## callees

- `0x1800135a8`
- `0x180019ce4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019d53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019d53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019d0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019d0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019d74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019d74`
- `DMCmnUtils!CopyString` at `0x180019d48`
- `DMCmnUtils!CopyString` at `0x180019d48`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PushMessage::GetHeaderValue(PushMessage *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  int HeaderValue; // ebx
  __int64 v8; // rcx
  HLOCAL hMem; // [rsp+60h] [rbp+8h] BYREF

  hMem = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_DWORD *)this + 4) > 2u && (v8 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL)) != 0 )
  {
    if ( *(_DWORD *)v8 == 1 )
      HeaderValue = CopyString(*(const unsigned __int16 **)(v8 + 16), 0xFFFFFFFF, (unsigned __int16 **)&hMem);
    else
      HeaderValue = -2147024883;
  }
  else
  {
    HeaderValue = -2147023728;
  }
  LeaveCriticalSection(v6);
  if ( HeaderValue >= 0 )
    HeaderValue = FindHeaderValue((unsigned __int16 *)hMem, a2, a3);
  LocalFree(hMem);
  return (unsigned int)HeaderValue;
}

```

## disassembly

```asm
0x180019ce4  push    rbx
0x180019ce6  push    rbp
0x180019ce7  push    rsi
0x180019ce8  push    rdi
0x180019ce9  sub     rsp, 38h
0x180019ced  mov     rsi, r8
0x180019cf0  mov     rbp, rdx
0x180019cf3  mov     rbx, rcx
0x180019cf6  mov     [rsp+58h+hMem], 0
0x180019cff  lea     rdi, [rcx+20h]
0x180019d03  mov     [rsp+58h+var_38], rdi
0x180019d08  mov     rcx, rdi; lpCriticalSection
0x180019d0b  call    cs:__imp_EnterCriticalSection
0x180019d11  mov     [rsp+58h+var_30], 1
0x180019d16  cmp     dword ptr [rbx+10h], 2
0x180019d1a  ja      short loc_180019D23
0x180019d1c  mov     ebx, 80070490h
0x180019d21  jmp     short loc_180019D50
0x180019d23  mov     rax, [rbx+8]
0x180019d27  mov     rcx, [rax+10h]
0x180019d2b  test    rcx, rcx
0x180019d2e  jz      short loc_180019D1C
0x180019d30  cmp     dword ptr [rcx], 1
0x180019d33  jz      short loc_180019D3C
0x180019d35  mov     ebx, 8007000Dh
0x180019d3a  jmp     short loc_180019D50
0x180019d3c  lea     r8, [rsp+58h+hMem]
0x180019d41  or      edx, 0FFFFFFFFh
0x180019d44  mov     rcx, [rcx+10h]
0x180019d48  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180019d4e  mov     ebx, eax
0x180019d50  mov     rcx, rdi; lpCriticalSection
0x180019d53  call    cs:__imp_LeaveCriticalSection
0x180019d59  test    ebx, ebx
0x180019d5b  js      short loc_180019D6F
0x180019d5d  mov     r8, rsi
0x180019d60  mov     rdx, rbp
0x180019d63  mov     rcx, [rsp+58h+hMem]
0x180019d68  call    FindHeaderValue
0x180019d6d  mov     ebx, eax
0x180019d6f  mov     rcx, [rsp+58h+hMem]; hMem
0x180019d74  call    cs:__imp_LocalFree
0x180019d7a  mov     eax, ebx
0x180019d7c  add     rsp, 38h
0x180019d80  pop     rdi
0x180019d81  pop     rsi
0x180019d82  pop     rbp
0x180019d83  pop     rbx
0x180019d84  retn
```
