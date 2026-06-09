# NDFSQMSession::GetResultData(_GUID const &,ushort const *)

- ea: `0x180024f78`
- end: `0x180025034`
- name: `?GetResultData@NDFSQMSession@@AEAAPEAUSQMRepairResultData@1@AEBU_GUID@@PEBG@Z`
- size: `188`
- prototype: `struct NDFSQMSession::SQMRepairResultData *__fastcall(NDFSQMSession *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800241a0`
- `0x180024240`
- `0x180024278`
- `0x180025f90`

## callees

- `0x18001dd74`
- `0x180024f78`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180025011`
- `KERNEL32!SetLastError` at `0x180025011`

## pseudocode

```c
struct NDFSQMSession::SQMRepairResultData *__fastcall NDFSQMSession::GetResultData(
        NDFSQMSession *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  _QWORD *i; // r9
  __int64 v7; // rax
  unsigned __int64 v8; // r10
  _QWORD *v9; // rcx
  unsigned __int64 v10; // r11
  unsigned __int64 v11; // rdx
  const unsigned __int16 *v12; // r8

  for ( i = (_QWORD *)*((_QWORD *)this + 3); ; i += 16 )
  {
    if ( i == *((_QWORD **)this + 4) )
    {
      SetLastError(0x80070490);
      return 0;
    }
    v7 = *(_QWORD *)((char *)i + 76) - *(_QWORD *)&a2->Data1;
    if ( !v7 )
      v7 = *(_QWORD *)((char *)i + 84) - *(_QWORD *)a2->Data4;
    if ( !v7 )
    {
      v8 = std::char_traits<unsigned short>::length(a3);
      v9 = i + 4;
      v10 = i[6];
      v11 = v8;
      if ( v10 < v8 )
        v11 = i[6];
      if ( i[7] >= 8u )
        v9 = (_QWORD *)*v9;
      if ( v11 )
      {
        v12 = a3;
        while ( v11 )
        {
          if ( *(_WORD *)v9 != *v12 )
            goto LABEL_18;
          v9 = (_QWORD *)((char *)v9 + 2);
          ++v12;
          --v11;
        }
      }
      if ( v10 == v8 )
        break;
    }
LABEL_18:
    ;
  }
  return (struct NDFSQMSession::SQMRepairResultData *)i;
}

```

## disassembly

```asm
0x180024f78  mov     [rsp+arg_8], rbx
0x180024f7d  mov     [rsp+arg_10], rsi
0x180024f82  push    rdi
0x180024f83  sub     rsp, 20h
0x180024f87  mov     rsi, r8
0x180024f8a  mov     rdi, rdx
0x180024f8d  mov     rbx, rcx
0x180024f90  mov     r9, [rcx+18h]
0x180024f94  cmp     r9, [rbx+20h]
0x180024f98  jnz     short loc_180024FA1
0x180024f9a  mov     ecx, 80070490h
0x180024f9f  jmp     short loc_180025011
0x180024fa1  mov     rax, [r9+4Ch]
0x180024fa5  sub     rax, [rdi]
0x180024fa8  jnz     short loc_180024FB2
0x180024faa  mov     rax, [r9+54h]
0x180024fae  sub     rax, [rdi+8]
0x180024fb2  test    rax, rax
0x180024fb5  jnz     short loc_180025029
0x180024fb7  mov     rcx, rsi
0x180024fba  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180024fbf  mov     r10, rax
0x180024fc2  lea     rcx, [r9+20h]
0x180024fc6  mov     r11, [r9+30h]
0x180024fca  mov     rdx, rax
0x180024fcd  cmp     r11, rax
0x180024fd0  cmovb   rdx, r11
0x180024fd4  cmp     qword ptr [rcx+18h], 8
0x180024fd9  jb      short loc_180024FDE
0x180024fdb  mov     rcx, [rcx]
0x180024fde  test    rdx, rdx
0x180024fe1  jz      short loc_180025001
0x180024fe3  mov     r8, rsi
0x180024fe6  test    rdx, rdx
0x180024fe9  jz      short loc_180025001
0x180024feb  movzx   eax, word ptr [r8]
0x180024fef  cmp     [rcx], ax
0x180024ff2  jnz     short loc_180025029
0x180024ff4  add     rcx, 2
0x180024ff8  add     r8, 2
0x180024ffc  dec     rdx
0x180024fff  jmp     short loc_180024FE6
0x180025001  cmp     r11, r10
0x180025004  jnz     short loc_180025029
0x180025006  mov     rax, r9
0x180025009  jmp     short loc_180025019
0x18002500b  jmp     short $+2
0x18002500d  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x180025011  call    cs:__imp_SetLastError
0x180025017  xor     eax, eax
0x180025019  mov     rbx, [rsp+28h+arg_8]
0x18002501e  mov     rsi, [rsp+28h+arg_10]
0x180025023  add     rsp, 20h
0x180025027  pop     rdi
0x180025028  retn
0x180025029  sub     r9, 0FFFFFFFFFFFFFF80h
0x18002502d  jmp     loc_180024F94
```
