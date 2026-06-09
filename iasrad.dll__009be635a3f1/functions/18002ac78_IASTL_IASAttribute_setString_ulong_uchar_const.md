# IASTL::IASAttribute::setString(ulong,uchar const *)

- ea: `0x18002ac78`
- end: `0x18002acf5`
- name: `?setString@IASAttribute@IASTL@@QEAAXKPEBE@Z`
- size: `125`
- prototype: `void __fastcall(IASTL::IASAttribute *__hidden this, size_t Size, const unsigned __int8 *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b118`
- `0x180024e00`

## callees

- `0x180002106`
- `0x18002a530`
- `0x18002a6bc`
- `0x18002ac78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ac9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ac9d`

## pseudocode

```c
void __fastcall IASTL::IASAttribute::setString(IASTL::IASAttribute *this, size_t Size, const unsigned __int8 *Src)
{
  size_t v3; // rbx
  _BYTE *v6; // rax
  int v7; // edx
  _BYTE *v8; // rdi

  v3 = (unsigned int)Size;
  if ( (int)Size + 1 < (unsigned int)Size )
    IASTL::issue_error((IASTL *)0x216, Size);
  v6 = CoTaskMemAlloc((unsigned int)(Size + 1));
  v8 = v6;
  if ( !v6 )
    IASTL::issue_error((IASTL *)0x8007000ELL, v7);
  memcpy_0(v6, Src, v3);
  v8[v3] = 0;
  IASTL::IASAttribute::clearValue(this);
  *(_QWORD *)(*(_QWORD *)this + 24LL) = v8;
  *(_QWORD *)(*(_QWORD *)this + 32LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 16LL) = 5;
}

```

## disassembly

```asm
0x18002ac78  push    rbx
0x18002ac7a  push    rbp
0x18002ac7b  push    rsi
0x18002ac7c  push    rdi
0x18002ac7d  sub     rsp, 28h
0x18002ac81  mov     ebx, edx
0x18002ac83  mov     rbp, r8
0x18002ac86  mov     rsi, rcx
0x18002ac89  lea     eax, [rbx+1]
0x18002ac8c  cmp     eax, edx
0x18002ac8e  jnb     short loc_18002AC9B
0x18002ac90  mov     ecx, 216h; this
0x18002ac95  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18002ac9b  mov     ecx, eax; cb
0x18002ac9d  call    cs:__imp_CoTaskMemAlloc
0x18002aca3  mov     rdi, rax
0x18002aca6  test    rax, rax
0x18002aca9  jnz     short loc_18002ACB6
0x18002acab  mov     ecx, 8007000Eh; this
0x18002acb0  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18002acb6  mov     r8, rbx; Size
0x18002acb9  mov     rdx, rbp; Src
0x18002acbc  mov     rcx, rdi; void *
0x18002acbf  call    memcpy_0
0x18002acc4  mov     rcx, rsi; this
0x18002acc7  mov     byte ptr [rbx+rdi], 0
0x18002accb  call    ?clearValue@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::clearValue(void)
0x18002acd0  mov     rax, [rsi]
0x18002acd3  mov     [rax+18h], rdi
0x18002acd7  mov     rax, [rsi]
0x18002acda  mov     qword ptr [rax+20h], 0
0x18002ace2  mov     rax, [rsi]
0x18002ace5  mov     dword ptr [rax+10h], 5
0x18002acec  add     rsp, 28h
0x18002acf0  pop     rdi
0x18002acf1  pop     rsi
0x18002acf2  pop     rbp
0x18002acf3  pop     rbx
0x18002acf4  retn
```
