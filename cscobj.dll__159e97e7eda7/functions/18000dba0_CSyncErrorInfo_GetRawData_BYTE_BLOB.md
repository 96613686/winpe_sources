# CSyncErrorInfo::GetRawData(_BYTE_BLOB * *)

- ea: `0x18000dba0`
- end: `0x18000dc2c`
- name: `?GetRawData@CSyncErrorInfo@@UEAAJPEAPEAU_BYTE_BLOB@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(CSyncErrorInfo *__hidden this, struct _BYTE_BLOB **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000dba0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dbbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dbbf`

## pseudocode

```c
__int64 __fastcall CSyncErrorInfo::GetRawData(CSyncErrorInfo *this, struct _BYTE_BLOB **a2)
{
  __int64 result; // rax
  char *v5; // rax

  result = 2147500035LL;
  if ( a2 )
  {
    v5 = (char *)CoTaskMemAlloc(0x80u);
    if ( v5 )
    {
      *(_DWORD *)v5 = 120;
      *(_OWORD *)(v5 + 4) = *((_OWORD *)this + 1);
      *(_OWORD *)(v5 + 20) = *((_OWORD *)this + 2);
      *(_OWORD *)(v5 + 36) = *((_OWORD *)this + 3);
      *(_OWORD *)(v5 + 52) = *((_OWORD *)this + 4);
      *(_OWORD *)(v5 + 68) = *((_OWORD *)this + 5);
      *(_OWORD *)(v5 + 84) = *((_OWORD *)this + 6);
      *(_OWORD *)(v5 + 100) = *((_OWORD *)this + 7);
      *(_QWORD *)(v5 + 116) = *((_QWORD *)this + 16);
      *a2 = (struct _BYTE_BLOB *)v5;
      return 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000dba0  mov     [rsp+arg_0], rbx
0x18000dba5  push    rdi
0x18000dba6  sub     rsp, 20h
0x18000dbaa  mov     rdi, rdx
0x18000dbad  mov     rbx, rcx
0x18000dbb0  mov     eax, 80004003h
0x18000dbb5  test    rdx, rdx
0x18000dbb8  jz      short loc_18000DC21
0x18000dbba  mov     ecx, 80h; cb
0x18000dbbf  call    cs:__imp_CoTaskMemAlloc
0x18000dbc5  test    rax, rax
0x18000dbc8  jnz     short loc_18000DBD1
0x18000dbca  mov     eax, 8007000Eh
0x18000dbcf  jmp     short loc_18000DC21
0x18000dbd1  mov     dword ptr [rax], 78h ; 'x'
0x18000dbd7  movups  xmm0, xmmword ptr [rbx+10h]
0x18000dbdb  movups  xmmword ptr [rax+4], xmm0
0x18000dbdf  movups  xmm1, xmmword ptr [rbx+20h]
0x18000dbe3  movups  xmmword ptr [rax+14h], xmm1
0x18000dbe7  movups  xmm0, xmmword ptr [rbx+30h]
0x18000dbeb  movups  xmmword ptr [rax+24h], xmm0
0x18000dbef  movups  xmm1, xmmword ptr [rbx+40h]
0x18000dbf3  movups  xmmword ptr [rax+34h], xmm1
0x18000dbf7  movups  xmm0, xmmword ptr [rbx+50h]
0x18000dbfb  movups  xmmword ptr [rax+44h], xmm0
0x18000dbff  movups  xmm1, xmmword ptr [rbx+60h]
0x18000dc03  movups  xmmword ptr [rax+54h], xmm1
0x18000dc07  movups  xmm0, xmmword ptr [rbx+70h]
0x18000dc0b  movups  xmmword ptr [rax+64h], xmm0
0x18000dc0f  movsd   xmm1, qword ptr [rbx+80h]
0x18000dc17  movsd   qword ptr [rax+74h], xmm1
0x18000dc1c  mov     [rdi], rax
0x18000dc1f  xor     eax, eax
0x18000dc21  mov     rbx, [rsp+28h+arg_0]
0x18000dc26  add     rsp, 20h
0x18000dc2a  pop     rdi
0x18000dc2b  retn
```
