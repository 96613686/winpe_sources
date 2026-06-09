# HrConvFromVTEMPTY(tagPROPVARIANT *,ushort)

- ea: `0x1800510c4`
- end: `0x180051177`
- name: `?HrConvFromVTEMPTY@@YAJPEAUtagPROPVARIANT@@G@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180051b64`

## callees

- `0x1800510c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051111`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051150`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051111`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051150`

## pseudocode

```c
__int64 __fastcall HrConvFromVTEMPTY(struct tagPROPVARIANT *a1, __int16 a2)
{
  unsigned int v2; // ebx
  GUID *v4; // rax
  _WORD *v5; // rcx

  v2 = 0;
  switch ( a2 )
  {
    case 20:
    case 21:
      goto LABEL_17;
    case 30:
      v4 = (GUID *)CoTaskMemAlloc(1u);
      if ( v4 )
      {
        LOBYTE(v4->Data1) = 0;
        goto LABEL_11;
      }
      return (unsigned int)-2147024882;
    case 31:
      v5 = CoTaskMemAlloc(2u);
      if ( v5 )
      {
        *v5 = 0;
        a1->hVal.QuadPart = (LONGLONG)v5;
        return v2;
      }
      return (unsigned int)-2147024882;
    case 64:
    case 65:
LABEL_17:
      a1->hVal.QuadPart = 0;
      return v2;
    case 72:
      v4 = (GUID *)CoTaskMemAlloc(0x10u);
      if ( v4 )
      {
        *v4 = GUID_NULL;
LABEL_11:
        a1->hVal.QuadPart = (LONGLONG)v4;
        return v2;
      }
      return (unsigned int)-2147024882;
  }
  return (unsigned int)-2147352571;
}

```

## disassembly

```asm
0x1800510c4  mov     [rsp+arg_0], rbx
0x1800510c9  push    rdi
0x1800510ca  sub     rsp, 20h
0x1800510ce  xor     ebx, ebx
0x1800510d0  movzx   r8d, dx
0x1800510d4  mov     rdi, rcx
0x1800510d7  sub     r8d, 14h
0x1800510db  jz      loc_180051166
0x1800510e1  sub     r8d, 1
0x1800510e5  jz      short loc_180051166
0x1800510e7  sub     r8d, 9
0x1800510eb  jz      short loc_18005114B
0x1800510ed  sub     r8d, 1
0x1800510f1  jz      short loc_18005112D
0x1800510f3  sub     r8d, 21h ; '!'
0x1800510f7  jz      short loc_180051166
0x1800510f9  sub     r8d, 1
0x1800510fd  jz      short loc_180051166
0x1800510ff  cmp     r8d, 7
0x180051103  jz      short loc_18005110C
0x180051105  mov     ebx, 80020005h
0x18005110a  jmp     short loc_18005116A
0x18005110c  mov     ecx, 10h; cb
0x180051111  call    cs:__imp_CoTaskMemAlloc
0x180051117  test    rax, rax
0x18005111a  jz      short loc_18005115F
0x18005111c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180051123  movdqu  xmmword ptr [rax], xmm0
0x180051127  mov     [rdi+8], rax
0x18005112b  jmp     short loc_18005116A
0x18005112d  mov     ecx, 2; cb
0x180051132  call    cs:__imp_CoTaskMemAlloc
0x180051138  mov     rcx, rax
0x18005113b  test    rax, rax
0x18005113e  jz      short loc_18005115F
0x180051140  xor     eax, eax
0x180051142  mov     [rcx], ax
0x180051145  mov     [rdi+8], rcx
0x180051149  jmp     short loc_18005116A
0x18005114b  mov     ecx, 1; cb
0x180051150  call    cs:__imp_CoTaskMemAlloc
0x180051156  test    rax, rax
0x180051159  jz      short loc_18005115F
0x18005115b  mov     [rax], bl
0x18005115d  jmp     short loc_180051127
0x18005115f  mov     ebx, 8007000Eh
0x180051164  jmp     short loc_18005116A
0x180051166  mov     [rcx+8], rbx
0x18005116a  mov     eax, ebx
0x18005116c  mov     rbx, [rsp+28h+arg_0]
0x180051171  add     rsp, 20h
0x180051175  pop     rdi
0x180051176  retn
```
