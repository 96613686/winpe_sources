# sub_1800D7EDC

- ea: `0x1800d7edc`
- end: `0x1800d81a4`
- name: `sub_1800D7EDC`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800d7910`

## callees

- `0x180002090`
- `0x180004690`
- `0x18000c7a0`
- `0x180010a70`
- `0x180014d40`
- `0x180024efc`
- `0x18009a6a0`
- `0x18009b28c`
- `0x1800d7edc`
- `0x1800d8344`
- `0x1800d8a44`
- `0x18011ef30`
- `0x18011f73c`
- `0x18012a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7f44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8036`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d80e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7f44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d8036`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d80e2`

## string_xrefs

- `0x1800d7f06`: `CMsbClient::OnRead`
- `0x1800d7f9b`: `CMsbClient::OnRead`
- `0x1800d808d`: `CMsbClient::OnRead`
- `0x1800d8139`: `CMsbClient::OnRead`

## pseudocode

```c
__int64 __fastcall sub_1800D7EDC(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  int v5; // edi
  __int64 v6; // r8
  __int64 (__fastcall ***v7)(); // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  _DWORD *v11; // rdi
  __int64 v12; // rdx
  __int64 (__fastcall ***v13)(); // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 (__fastcall ***v17)(); // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  char v21; // [rsp+60h] [rbp+8h] BYREF
  __int64 v22; // [rsp+70h] [rbp+18h] BYREF

  sub_180004690((PSRWLOCK)(a1 + 48));
  v22 = 0;
  sub_180010A70(&v21, "CMsbClient::OnRead", 878);
  v5 = sub_18011F73C(*(_QWORD *)(a1 + 360), a2, &v22);
  if ( v5 >= 0 )
  {
    v11 = (_DWORD *)(a1 + 8);
    if ( (unsigned __int8)byte_18015750C >= 0x10u )
      sub_1800D8A44(*((_QWORD *)RequestContext + 22), v4, v6, a1, a2, v22, *v11);
    if ( (*(_BYTE *)v11 & 0x30) == 0 && (*(_BYTE *)v11 & 0xC) != 0 )
    {
      v5 = sub_1800D8344(a1, v22);
      if ( v5 >= 0 )
      {
        v5 = sub_18011EF30(*(_QWORD *)(a1 + 360), a1 + 32, 0);
        if ( v5 < 0 )
        {
          v17 = (__int64 (__fastcall ***)())qword_1801576B0;
          if ( !qword_1801576B0 )
          {
            v18 = MFGetCallStackTracingWeakReference(0, v16);
            qword_1801576B0 = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v17 = (__int64 (__fastcall ***)())qword_1801576B0;
            }
            else
            {
              v17 = &off_180156520;
              qword_1801576B0 = (__int64)&off_180156520;
            }
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            v19 = sub_180024EFC(v17);
            if ( *(_DWORD *)(v19 + 1996) != v5 )
              sub_18009A6A0(v19, "CMsbClient::OnRead", 899, (unsigned int)v5);
          }
          if ( byte_180157508 )
          {
            v10 = 75;
            goto LABEL_37;
          }
        }
      }
      else
      {
        v13 = (__int64 (__fastcall ***)())qword_1801576B0;
        if ( !qword_1801576B0 )
        {
          v14 = MFGetCallStackTracingWeakReference(0, v12);
          qword_1801576B0 = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (__int64 (__fastcall ***)())qword_1801576B0;
          }
          else
          {
            v13 = &off_180156520;
            qword_1801576B0 = (__int64)&off_180156520;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v15 = sub_180024EFC(v13);
          if ( *(_DWORD *)(v15 + 1996) != v5 )
            sub_18009A6A0(v15, "CMsbClient::OnRead", 897, (unsigned int)v5);
        }
        if ( byte_180157508 )
        {
          v10 = 74;
          goto LABEL_37;
        }
      }
    }
  }
  else
  {
    v7 = (__int64 (__fastcall ***)())qword_1801576B0;
    if ( !qword_1801576B0 )
    {
      v8 = MFGetCallStackTracingWeakReference(0, v4);
      qword_1801576B0 = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 (__fastcall ***)())qword_1801576B0;
      }
      else
      {
        v7 = &off_180156520;
        qword_1801576B0 = (__int64)&off_180156520;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = sub_180024EFC(v7);
      if ( *(_DWORD *)(v9 + 1996) != v5 )
        sub_18009A6A0(v9, "CMsbClient::OnRead", 878, (unsigned int)v5);
    }
    if ( byte_180157508 )
    {
      v10 = 72;
LABEL_37:
      sub_180014D40(*((_QWORD *)RequestContext + 2), v10, &stru_180145070, a1, v5);
    }
  }
  sub_180002090(&v21);
  sub_18000C7A0(&v22);
  return sub_18009B28C(a1 + 48);
}

```

## disassembly

```asm
0x1800d7edc  mov     [rsp+arg_8], rbx
0x1800d7ee1  push    rbp
0x1800d7ee2  push    rsi
0x1800d7ee3  push    rdi
0x1800d7ee4  sub     rsp, 40h
0x1800d7ee8  mov     rbx, rcx
0x1800d7eeb  mov     rsi, rdx
0x1800d7eee  add     rcx, 30h ; '0'; SRWLock
0x1800d7ef2  call    sub_180004690
0x1800d7ef7  mov     r8d, 36Eh
0x1800d7efd  mov     [rsp+58h+arg_10], 0
0x1800d7f06  lea     rdx, aCmsbclientOnre; "CMsbClient::OnRead"
0x1800d7f0d  lea     rcx, [rsp+58h+arg_0]
0x1800d7f12  call    sub_180010A70
0x1800d7f17  mov     rcx, [rbx+168h]
0x1800d7f1e  lea     r8, [rsp+58h+arg_10]
0x1800d7f23  xor     r9d, r9d
0x1800d7f26  mov     rdx, rsi
0x1800d7f29  call    sub_18011F73C
0x1800d7f2e  mov     edi, eax
0x1800d7f30  test    eax, eax
0x1800d7f32  jns     loc_1800D7FC7
0x1800d7f38  mov     rcx, cs:qword_1801576B0
0x1800d7f3f  test    rcx, rcx
0x1800d7f42  jnz     short loc_1800D7F85
0x1800d7f44  call    cs:MFGetCallStackTracingWeakReference
0x1800d7f4a  mov     cs:qword_1801576B0, rax
0x1800d7f51  mov     rcx, rax
0x1800d7f54  test    rax, rax
0x1800d7f57  jz      short loc_1800D7F77
0x1800d7f59  mov     rax, [rax]
0x1800d7f5c  mov     edx, 7F0h
0x1800d7f61  mov     rax, [rax+8]
0x1800d7f65  call    j__guard_dispatch_icall
0x1800d7f6a  test    eax, eax
0x1800d7f6c  jz      short loc_1800D7F77
0x1800d7f6e  mov     rcx, cs:qword_1801576B0
0x1800d7f75  jmp     short loc_1800D7F85
0x1800d7f77  lea     rcx, off_180156520
0x1800d7f7e  mov     cs:qword_1801576B0, rcx
0x1800d7f85  cmp     byte ptr [rcx+8], 0
0x1800d7f89  jz      short loc_1800D7FB0
0x1800d7f8b  call    sub_180024EFC
0x1800d7f90  cmp     [rax+7CCh], edi
0x1800d7f96  jz      short loc_1800D7FB0
0x1800d7f98  mov     r9d, edi
0x1800d7f9b  lea     rdx, aCmsbclientOnre; "CMsbClient::OnRead"
0x1800d7fa2  mov     r8d, 36Eh
0x1800d7fa8  mov     rcx, rax
0x1800d7fab  call    sub_18009A6A0
0x1800d7fb0  cmp     cs:byte_180157508, 1
0x1800d7fb7  jb      loc_1800D817A
0x1800d7fbd  mov     edx, 48h ; 'H'
0x1800d7fc2  jmp     loc_1800D815C
0x1800d7fc7  cmp     cs:byte_18015750C, 10h
0x1800d7fce  lea     rdi, [rbx+8]
0x1800d7fd2  jb      short loc_1800D7FFF
0x1800d7fd4  mov     eax, [rdi]
0x1800d7fd6  mov     r9, rbx
0x1800d7fd9  mov     rcx, cs:RequestContext
0x1800d7fe0  mov     [rsp+58h+var_28], eax
0x1800d7fe4  mov     rax, [rsp+58h+arg_10]
0x1800d7fe9  mov     [rsp+58h+var_30], rax
0x1800d7fee  mov     rcx, [rcx+0B0h]
0x1800d7ff5  mov     [rsp+58h+var_38], rsi
0x1800d7ffa  call    sub_1800D8A44
0x1800d7fff  test    byte ptr [rdi], 30h
0x1800d8002  setz    cl
0x1800d8005  test    byte ptr [rdi], 0Ch
0x1800d8008  setnz   al
0x1800d800b  test    al, cl
0x1800d800d  jz      loc_1800D817A
0x1800d8013  mov     rdx, [rsp+58h+arg_10]
0x1800d8018  mov     rcx, rbx
0x1800d801b  call    sub_1800D8344
0x1800d8020  mov     edi, eax
0x1800d8022  test    eax, eax
0x1800d8024  jns     loc_1800D80B9
0x1800d802a  mov     rcx, cs:qword_1801576B0
0x1800d8031  test    rcx, rcx
0x1800d8034  jnz     short loc_1800D8077
0x1800d8036  call    cs:MFGetCallStackTracingWeakReference
0x1800d803c  mov     cs:qword_1801576B0, rax
0x1800d8043  mov     rcx, rax
0x1800d8046  test    rax, rax
0x1800d8049  jz      short loc_1800D8069
0x1800d804b  mov     rax, [rax]
0x1800d804e  mov     edx, 7F0h
0x1800d8053  mov     rax, [rax+8]
0x1800d8057  call    j__guard_dispatch_icall
0x1800d805c  test    eax, eax
0x1800d805e  jz      short loc_1800D8069
0x1800d8060  mov     rcx, cs:qword_1801576B0
0x1800d8067  jmp     short loc_1800D8077
0x1800d8069  lea     rcx, off_180156520
0x1800d8070  mov     cs:qword_1801576B0, rcx
0x1800d8077  cmp     byte ptr [rcx+8], 0
0x1800d807b  jz      short loc_1800D80A2
0x1800d807d  call    sub_180024EFC
0x1800d8082  cmp     [rax+7CCh], edi
0x1800d8088  jz      short loc_1800D80A2
0x1800d808a  mov     r9d, edi
0x1800d808d  lea     rdx, aCmsbclientOnre; "CMsbClient::OnRead"
0x1800d8094  mov     r8d, 381h
0x1800d809a  mov     rcx, rax
0x1800d809d  call    sub_18009A6A0
0x1800d80a2  cmp     cs:byte_180157508, 1
0x1800d80a9  jb      loc_1800D817A
0x1800d80af  mov     edx, 4Ah ; 'J'
0x1800d80b4  jmp     loc_1800D815C
0x1800d80b9  mov     rcx, [rbx+168h]
0x1800d80c0  lea     rdx, [rbx+20h]
0x1800d80c4  xor     r8d, r8d
0x1800d80c7  call    sub_18011EF30
0x1800d80cc  mov     edi, eax
0x1800d80ce  test    eax, eax
0x1800d80d0  jns     loc_1800D817A
0x1800d80d6  mov     rcx, cs:qword_1801576B0
0x1800d80dd  test    rcx, rcx
0x1800d80e0  jnz     short loc_1800D8123
0x1800d80e2  call    cs:MFGetCallStackTracingWeakReference
0x1800d80e8  mov     cs:qword_1801576B0, rax
0x1800d80ef  mov     rcx, rax
0x1800d80f2  test    rax, rax
0x1800d80f5  jz      short loc_1800D8115
0x1800d80f7  mov     rax, [rax]
0x1800d80fa  mov     edx, 7F0h
0x1800d80ff  mov     rax, [rax+8]
0x1800d8103  call    j__guard_dispatch_icall
0x1800d8108  test    eax, eax
0x1800d810a  jz      short loc_1800D8115
0x1800d810c  mov     rcx, cs:qword_1801576B0
0x1800d8113  jmp     short loc_1800D8123
0x1800d8115  lea     rcx, off_180156520
0x1800d811c  mov     cs:qword_1801576B0, rcx
0x1800d8123  cmp     byte ptr [rcx+8], 0
0x1800d8127  jz      short loc_1800D814E
0x1800d8129  call    sub_180024EFC
0x1800d812e  cmp     [rax+7CCh], edi
0x1800d8134  jz      short loc_1800D814E
0x1800d8136  mov     r9d, edi
0x1800d8139  lea     rdx, aCmsbclientOnre; "CMsbClient::OnRead"
0x1800d8140  mov     r8d, 383h
0x1800d8146  mov     rcx, rax
0x1800d8149  call    sub_18009A6A0
0x1800d814e  cmp     cs:byte_180157508, 1
0x1800d8155  jb      short loc_1800D817A
0x1800d8157  mov     edx, 4Bh ; 'K'
0x1800d815c  mov     rcx, cs:RequestContext
0x1800d8163  lea     r8, stru_180145070
0x1800d816a  mov     r9, rbx
0x1800d816d  mov     dword ptr [rsp+58h+var_38], edi
0x1800d8171  mov     rcx, [rcx+10h]
0x1800d8175  call    sub_180014D40
0x1800d817a  lea     rcx, [rsp+58h+arg_0]
0x1800d817f  call    sub_180002090
0x1800d8184  lea     rcx, [rsp+58h+arg_10]
0x1800d8189  call    sub_18000C7A0
0x1800d818e  lea     rcx, [rbx+30h]
0x1800d8192  call    sub_18009B28C
0x1800d8197  mov     rbx, [rsp+58h+arg_8]
0x1800d819c  add     rsp, 40h
0x1800d81a0  pop     rdi
0x1800d81a1  pop     rsi
0x1800d81a2  pop     rbp
0x1800d81a3  retn
```
