# CADMCOMW::DeleteKey(ulong,ushort const *)

- ea: `0x1800041a0`
- end: `0x1800042b6`
- name: `?DeleteKey@CADMCOMW@@UEAAJKPEBG@Z`
- size: `278`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000238c`
- `0x1800041a0`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::DeleteKey(CADMCOMW *this, unsigned int a2, unsigned __int16 *a3)
{
  signed int v6; // ebx
  __int64 v7; // rcx
  signed int v8; // eax
  int v10; // [rsp+60h] [rbp-28h] BYREF
  __int64 v11; // [rsp+68h] [rbp-20h] BYREF
  unsigned int v12; // [rsp+A0h] [rbp+18h] BYREF
  int v13; // [rsp+A8h] [rbp+20h] BYREF

  v12 = 0;
  v13 = 0;
  v10 = 0;
  if ( a3 )
  {
    v6 = CADMCOMW::LookupAndAccessCheck(this, a2, &v12, (__int64)a3, 0, 2, 0, 0, &v11, &v13, (__int64)&v10);
    if ( v6 >= 0 )
    {
      v7 = *((_QWORD *)this + 101);
      if ( v7 && v13 == 1 )
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v7 + 104LL))(v7, v12, a3);
      else
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 4) + 72LL))(
               *((_QWORD *)this + 4),
               v12,
               a3);
      v6 = v8;
    }
    if ( v10 )
      CADMCOMW::AuditAccess(this, 0x1195u, v6, a2, a3, 0, 0, 0, 0, 0, 0);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800041a0  mov     rax, rsp
0x1800041a3  mov     [rax+8], rbx
0x1800041a7  mov     [rax+10h], rbp
0x1800041ab  push    rsi
0x1800041ac  push    rdi
0x1800041ad  push    r14
0x1800041af  sub     rsp, 70h
0x1800041b3  xor     r14d, r14d
0x1800041b6  mov     rdi, r8
0x1800041b9  mov     [rax+18h], r14d
0x1800041bd  mov     ebp, edx
0x1800041bf  mov     [rax+20h], r14d
0x1800041c3  mov     rsi, rcx
0x1800041c6  mov     [rax-28h], r14d
0x1800041ca  test    r8, r8
0x1800041cd  jnz     short loc_1800041D9
0x1800041cf  mov     ebx, 80070057h
0x1800041d4  jmp     loc_18000429F
0x1800041d9  lea     rax, [rsp+88h+var_28]
0x1800041de  mov     r9, rdi
0x1800041e1  mov     [rsp+88h+var_38], rax
0x1800041e6  lea     r8, [rsp+88h+arg_10]
0x1800041ee  lea     rax, [rsp+88h+arg_18]
0x1800041f6  mov     [rsp+88h+var_40], rax
0x1800041fb  lea     rax, [rsp+88h+var_20]
0x180004200  mov     [rsp+88h+var_48], rax
0x180004205  mov     qword ptr [rsp+88h+var_50], r14
0x18000420a  mov     [rsp+88h+var_58], r14
0x18000420f  mov     [rsp+88h+var_60], 2
0x180004217  mov     dword ptr [rsp+88h+var_68], r14d
0x18000421c  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180004221  mov     ebx, eax
0x180004223  test    eax, eax
0x180004225  js      short loc_180004262
0x180004227  mov     rcx, [rsi+328h]
0x18000422e  test    rcx, rcx
0x180004231  jz      short loc_180004246
0x180004233  cmp     [rsp+88h+arg_18], 1
0x18000423b  jnz     short loc_180004246
0x18000423d  mov     rax, [rcx]
0x180004240  mov     rax, [rax+68h]
0x180004244  jmp     short loc_180004251
0x180004246  mov     rcx, [rsi+20h]
0x18000424a  mov     rax, [rcx]
0x18000424d  mov     rax, [rax+48h]
0x180004251  mov     edx, [rsp+88h+arg_10]
0x180004258  mov     r8, rdi
0x18000425b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004260  mov     ebx, eax
0x180004262  cmp     [rsp+88h+var_28], r14d
0x180004267  jz      short loc_18000429F
0x180004269  mov     [rsp+88h+var_38], r14; unsigned __int16 *
0x18000426e  mov     r9d, ebp; unsigned int
0x180004271  mov     [rsp+88h+var_40], r14; struct _METADATA_RECORD *
0x180004276  mov     r8d, ebx; int
0x180004279  mov     [rsp+88h+var_48], r14; struct _METADATA_RECORD *
0x18000427e  mov     edx, 1195h; unsigned int
0x180004283  mov     [rsp+88h+var_50], r14d; unsigned int
0x180004288  mov     rcx, rsi; this
0x18000428b  mov     [rsp+88h+var_58], r14; unsigned __int16 *
0x180004290  mov     [rsp+88h+var_60], r14d; unsigned int
0x180004295  mov     [rsp+88h+var_68], rdi; unsigned __int16 *
0x18000429a  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x18000429f  lea     r11, [rsp+88h+var_18]
0x1800042a4  mov     eax, ebx
0x1800042a6  mov     rbx, [r11+20h]
0x1800042aa  mov     rbp, [r11+28h]
0x1800042ae  mov     rsp, r11
0x1800042b1  pop     r14
0x1800042b3  pop     rdi
0x1800042b4  pop     rsi
0x1800042b5  retn
```
