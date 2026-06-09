# CLTPartitionRoles::ValidateAndUpdateQueryInfo(ulong,ulong,__MIDL___MIDL_itf_stable_0000_0000_0002 *)

- ea: `0x18004fab8`
- end: `0x18004fc35`
- name: `?ValidateAndUpdateQueryInfo@CLTPartitionRoles@@AEAAJKKPEAU__MIDL___MIDL_itf_stable_0000_0000_0002@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(CLTPartitionRoles *__hidden this, unsigned int, unsigned int, struct __MIDL___MIDL_itf_stable_0000_0000_0002 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18004f600`

## callees

- `0x180001e60`
- `0x180015594`
- `0x18004fab8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fb1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fbb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fb1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fbb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004fb8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004fb8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTPartitionRoles::ValidateAndUpdateQueryInfo(
        CLTPartitionRoles *this,
        int a2,
        unsigned int a3,
        struct __MIDL___MIDL_itf_stable_0000_0000_0002 *a4)
{
  __int64 i; // rdi
  int v8; // ebx
  void *v9; // rcx
  int v10; // ecx
  const unsigned __int16 *v11; // rcx
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rax
  _OWORD *v14; // rax
  __int64 v15; // rax

  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    if ( *((_DWORD *)a4 + 6 * i + 3) <= 0xF0000000 )
      break;
  }
  if ( a2 != 1 || a3 - (unsigned int)i - 1 > 1 )
    return 2147942487LL;
  v8 = 0;
  *((GUID *)this + 4) = GUID_NULL;
  v9 = (void *)*((_QWORD *)this + 10);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)this + 10) = 0;
  }
  while ( (unsigned int)i < a3 )
  {
    v10 = *((_DWORD *)a4 + 6 * i + 3);
    if ( v10 )
    {
      if ( v10 != 1 )
        goto LABEL_25;
      if ( *((_DWORD *)a4 + 6 * i + 4) != 130 )
        goto LABEL_25;
      if ( *((_DWORD *)a4 + 6 * i + 2) )
        goto LABEL_25;
      v11 = (const unsigned __int16 *)*((_QWORD *)a4 + 3 * i);
      if ( !v11 )
        goto LABEL_25;
      v12 = safe_lstrlenW(v11) + 1;
      v13 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v12, 2u));
      *((_QWORD *)this + 10) = v13;
      if ( !v13 )
      {
        v8 = -2147024882;
        break;
      }
      v8 = StringCchCopyW(v13, v12, *((const unsigned __int16 **)a4 + 3 * i));
      if ( v8 < 0 )
      {
        CoTaskMemFree(*((LPVOID *)this + 10));
        *((_QWORD *)this + 10) = 0;
        break;
      }
    }
    else
    {
      if ( *((_DWORD *)a4 + 6 * i + 4) != 72
        || *((_DWORD *)a4 + 6 * i + 2)
        || (v14 = (_OWORD *)*((_QWORD *)a4 + 3 * i)) == 0 )
      {
LABEL_25:
        v8 = -2147024809;
        break;
      }
      *((_OWORD *)this + 4) = *v14;
    }
    i = (unsigned int)(i + 1);
  }
  v15 = *(_QWORD *)&GUID_NULL.Data1 - *((_QWORD *)this + 8);
  if ( *(_QWORD *)&GUID_NULL.Data1 == *((_QWORD *)this + 8) )
    v15 = *(_QWORD *)GUID_NULL.Data4 - *((_QWORD *)this + 9);
  if ( !v15 )
    return (unsigned int)-2147024809;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004fab8  push    rbx
0x18004faba  push    rbp
0x18004fabb  push    rsi
0x18004fabc  push    rdi
0x18004fabd  push    r12
0x18004fabf  push    r14
0x18004fac1  push    r15
0x18004fac3  sub     rsp, 20h
0x18004fac7  mov     rsi, r9
0x18004faca  mov     r12d, r8d
0x18004facd  mov     r15, rcx
0x18004fad0  xor     edi, edi
0x18004fad2  test    r8d, r8d
0x18004fad5  jz      short loc_18004FAED
0x18004fad7  lea     r9, [rdi+rdi*2]
0x18004fadb  cmp     dword ptr [rsi+r9*8+0Ch], 0F0000000h
0x18004fae4  jbe     short loc_18004FAED
0x18004fae6  inc     edi
0x18004fae8  cmp     edi, r12d
0x18004faeb  jb      short loc_18004FAD7
0x18004faed  cmp     edx, 1
0x18004faf0  jnz     loc_18004FC21
0x18004faf6  mov     eax, r12d
0x18004faf9  sub     eax, edi
0x18004fafb  dec     eax
0x18004fafd  cmp     eax, edx
0x18004faff  ja      loc_18004FC21
0x18004fb05  xor     ebx, ebx
0x18004fb07  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004fb0e  movdqu  xmmword ptr [rcx+40h], xmm0
0x18004fb13  mov     rcx, [rcx+50h]; pv
0x18004fb17  test    rcx, rcx
0x18004fb1a  jz      short loc_18004FB27
0x18004fb1c  call    cs:__imp_CoTaskMemFree
0x18004fb22  nop
0x18004fb23  mov     [r15+50h], rbx
0x18004fb27  mov     r14d, 80070057h
0x18004fb2d  jmp     loc_18004FBE9
0x18004fb32  lea     rbp, [rdi+rdi*2]
0x18004fb36  mov     ecx, [rsi+rbp*8+0Ch]
0x18004fb3a  test    ecx, ecx
0x18004fb3c  jz      loc_18004FBC7
0x18004fb42  cmp     ecx, 1
0x18004fb45  jnz     loc_18004FBFB
0x18004fb4b  cmp     dword ptr [rsi+rbp*8+10h], 82h
0x18004fb53  jnz     loc_18004FBFB
0x18004fb59  cmp     dword ptr [rsi+rbp*8+8], 0
0x18004fb5e  jnz     loc_18004FBFB
0x18004fb64  mov     rcx, [rsi+rbp*8]; unsigned __int16 *
0x18004fb68  test    rcx, rcx
0x18004fb6b  jz      loc_18004FBFB
0x18004fb71  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004fb76  lea     ebx, [rax+1]
0x18004fb79  mov     eax, 2
0x18004fb7e  mul     rbx
0x18004fb81  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004fb88  cmovb   rax, rcx
0x18004fb8c  mov     rcx, rax; cb
0x18004fb8f  call    cs:__imp_CoTaskMemAlloc
0x18004fb95  mov     [r15+50h], rax
0x18004fb99  test    rax, rax
0x18004fb9c  jz      short loc_18004FBF4
0x18004fb9e  mov     r8, [rsi+rbp*8]; unsigned __int16 *
0x18004fba2  mov     edx, ebx; unsigned __int64
0x18004fba4  mov     rcx, rax; unsigned __int16 *
0x18004fba7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004fbac  mov     ebx, eax
0x18004fbae  test    eax, eax
0x18004fbb0  jns     short loc_18004FBE7
0x18004fbb2  mov     rcx, [r15+50h]; pv
0x18004fbb6  call    cs:__imp_CoTaskMemFree
0x18004fbbc  nop
0x18004fbbd  mov     qword ptr [r15+50h], 0
0x18004fbc5  jmp     short loc_18004FBFE
0x18004fbc7  cmp     dword ptr [rsi+rbp*8+10h], 48h ; 'H'
0x18004fbcc  jnz     short loc_18004FBFB
0x18004fbce  cmp     dword ptr [rsi+rbp*8+8], 0
0x18004fbd3  jnz     short loc_18004FBFB
0x18004fbd5  mov     rax, [rsi+rbp*8]
0x18004fbd9  test    rax, rax
0x18004fbdc  jz      short loc_18004FBFB
0x18004fbde  movups  xmm0, xmmword ptr [rax]
0x18004fbe1  movdqu  xmmword ptr [r15+40h], xmm0
0x18004fbe7  inc     edi
0x18004fbe9  cmp     edi, r12d
0x18004fbec  jb      loc_18004FB32
0x18004fbf2  jmp     short loc_18004FBFE
0x18004fbf4  mov     ebx, 8007000Eh
0x18004fbf9  jmp     short loc_18004FBFE
0x18004fbfb  mov     ebx, r14d
0x18004fbfe  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18004fc05  sub     rax, [r15+40h]
0x18004fc09  jnz     short loc_18004FC16
0x18004fc0b  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18004fc12  sub     rax, [r15+48h]
0x18004fc16  test    rax, rax
0x18004fc19  cmovz   ebx, r14d
0x18004fc1d  mov     eax, ebx
0x18004fc1f  jmp     short loc_18004FC26
0x18004fc21  mov     eax, 80070057h
0x18004fc26  add     rsp, 20h
0x18004fc2a  pop     r15
0x18004fc2c  pop     r14
0x18004fc2e  pop     r12
0x18004fc30  pop     rdi
0x18004fc31  pop     rsi
0x18004fc32  pop     rbp
0x18004fc33  pop     rbx
0x18004fc34  retn
```
