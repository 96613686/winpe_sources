# CADMCOMW::DisableHistory(ulong *,ulong *)

- ea: `0x180004388`
- end: `0x180004556`
- name: `?DisableHistory@CADMCOMW@@AEAAJPEAK0@Z`
- size: `462`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008ae0`

## callees

- `0x180004388`
- `0x1800093bc`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::DisableHistory(CADMCOMW *this, unsigned int *a2, unsigned int *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  int v10; // eax
  unsigned int v12; // [rsp+40h] [rbp-29h] BYREF
  int v13; // [rsp+44h] [rbp-25h] BYREF
  __int64 v14; // [rsp+48h] [rbp-21h] BYREF
  int v15; // [rsp+50h] [rbp-19h]
  int v16; // [rsp+54h] [rbp-15h]
  __int64 v17; // [rsp+58h] [rbp-11h]
  unsigned int *v18; // [rsp+60h] [rbp-9h]
  __int64 v19; // [rsp+68h] [rbp-1h]
  __int64 v20; // [rsp+70h] [rbp+7h] BYREF
  int v21; // [rsp+78h] [rbp+Fh]
  int v22; // [rsp+7Ch] [rbp+13h]
  __int64 v23; // [rsp+80h] [rbp+17h]
  unsigned int *v24; // [rsp+88h] [rbp+1Fh]
  __int64 v25; // [rsp+90h] [rbp+27h]
  unsigned int v26; // [rsp+E8h] [rbp+7Fh] BYREF

  v20 = 9996;
  v26 = 0;
  v24 = &v26;
  v12 = 0;
  v13 = 0;
  v21 = 1;
  v22 = 1;
  v15 = 1;
  v16 = 1;
  v23 = 4;
  v25 = 0;
  v14 = 9998;
  v17 = 4;
  v18 = &v12;
  v19 = 0;
  if ( a2 && a3 )
  {
    v6 = *((_QWORD *)this + 4);
    *a2 = 0;
    *a3 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *))(*(_QWORD *)v6 + 280LL))(v6, 0, L"/LM");
    v8 = v7;
    if ( v7 == -2147024893 )
    {
      return 0;
    }
    else if ( v7 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, __int64 *, int *))(**((_QWORD **)this + 4)
                                                                                                 + 168LL))(
             *((_QWORD *)this + 4),
             0,
             &byte_1800127D8,
             &v14,
             &v13);
      v8 = 0;
      if ( v9 != -2146646015 )
        v8 = v9;
      if ( v8 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, __int64 *, int *))(**((_QWORD **)this + 4) + 168LL))(
                *((_QWORD *)this + 4),
                0,
                &byte_1800127D8,
                &v20,
                &v13);
        v8 = 0;
        if ( v10 != -2146646015 )
          v8 = v10;
        if ( v8 >= 0 && (v26 || v12) )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 288LL))(*((_QWORD *)this + 4), 0);
          v8 = CADMCOMW::SetHistoryAndEWR(this, 0, 0);
          if ( v8 >= 0 )
          {
            *a2 = v26;
            *a3 = v12;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004388  mov     [rsp-8+arg_0], rbx
0x18000438d  push    rbp
0x18000438e  push    rsi
0x18000438f  push    rdi
0x180004390  push    r14
0x180004392  push    r15
0x180004394  lea     rbp, [rsp-37h]
0x180004399  sub     rsp, 0A0h
0x1800043a0  xor     r15d, r15d
0x1800043a3  mov     [rbp+57h+var_50], 270Ch
0x1800043ab  mov     [rbp+57h+arg_18], r15d
0x1800043af  lea     rax, [rbp+57h+arg_18]
0x1800043b3  mov     [rbp+57h+var_38], rax
0x1800043b7  lea     rax, [rbp+57h+var_80]
0x1800043bb  mov     [rbp+57h+var_80], r15d
0x1800043bf  mov     rsi, r8
0x1800043c2  mov     [rbp+57h+var_7C], r15d
0x1800043c6  lea     r9d, [r15+1]
0x1800043ca  mov     [rbp+57h+var_48], r9d
0x1800043ce  mov     r14, rdx
0x1800043d1  mov     [rbp+57h+var_44], r9d
0x1800043d5  mov     rdi, rcx
0x1800043d8  mov     [rbp+57h+var_70], r9d
0x1800043dc  mov     [rbp+57h+var_6C], r9d
0x1800043e0  mov     [rbp+57h+arg_8], r15d
0x1800043e4  mov     [rbp+57h+var_40], 4
0x1800043ec  mov     [rbp+57h+var_30], r15
0x1800043f0  mov     [rbp+57h+var_78], 270Eh
0x1800043f8  mov     [rbp+57h+var_68], 4
0x180004400  mov     [rbp+57h+var_60], rax
0x180004404  mov     [rbp+57h+var_58], r15
0x180004408  test    rdx, rdx
0x18000440b  jz      loc_180004538
0x180004411  test    r8, r8
0x180004414  jz      loc_180004538
0x18000441a  mov     rcx, [rcx+20h]
0x18000441e  mov     [rdx], r15d
0x180004421  lea     rdx, [rbp+57h+arg_8]
0x180004425  mov     [rsp+0C0h+var_98], rdx
0x18000442a  xor     edx, edx
0x18000442c  mov     [r8], r15d
0x18000442f  lea     r8, aLm; "/LM"
0x180004436  mov     rax, [rcx]
0x180004439  mov     dword ptr [rsp+0C0h+var_A0], 1388h
0x180004441  mov     rax, [rax+118h]
0x180004448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000444d  mov     ebx, eax
0x18000444f  cmp     eax, 80070003h
0x180004454  jnz     short loc_18000445E
0x180004456  mov     ebx, r15d
0x180004459  jmp     loc_18000451C
0x18000445e  test    eax, eax
0x180004460  js      loc_18000451C
0x180004466  mov     rcx, [rdi+20h]
0x18000446a  lea     rdx, [rbp+57h+var_7C]
0x18000446e  mov     [rsp+0C0h+var_A0], rdx
0x180004473  lea     r9, [rbp+57h+var_78]
0x180004477  mov     edx, [rbp+57h+arg_8]
0x18000447a  lea     r8, byte_1800127D8
0x180004481  mov     rax, [rcx]
0x180004484  mov     rax, [rax+0A8h]
0x18000448b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004490  cmp     eax, 800CC801h
0x180004495  mov     ebx, r15d
0x180004498  cmovnz  ebx, eax
0x18000449b  test    ebx, ebx
0x18000449d  js      short loc_18000451C
0x18000449f  mov     rcx, [rdi+20h]
0x1800044a3  lea     rdx, [rbp+57h+var_7C]
0x1800044a7  mov     [rsp+0C0h+var_A0], rdx
0x1800044ac  lea     r9, [rbp+57h+var_50]
0x1800044b0  mov     edx, [rbp+57h+arg_8]
0x1800044b3  lea     r8, byte_1800127D8
0x1800044ba  mov     rax, [rcx]
0x1800044bd  mov     rax, [rax+0A8h]
0x1800044c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044c9  cmp     eax, 800CC801h
0x1800044ce  mov     ebx, r15d
0x1800044d1  cmovnz  ebx, eax
0x1800044d4  test    ebx, ebx
0x1800044d6  js      short loc_18000451C
0x1800044d8  cmp     [rbp+57h+arg_18], r15d
0x1800044dc  jnz     short loc_1800044E4
0x1800044de  cmp     [rbp+57h+var_80], r15d
0x1800044e2  jz      short loc_18000451C
0x1800044e4  mov     rcx, [rdi+20h]
0x1800044e8  mov     edx, [rbp+57h+arg_8]
0x1800044eb  mov     rax, [rcx]
0x1800044ee  mov     rax, [rax+120h]
0x1800044f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fa  xor     r8d, r8d; unsigned int
0x1800044fd  mov     [rbp+57h+arg_8], r15d
0x180004501  xor     edx, edx; unsigned int
0x180004503  mov     rcx, rdi; this
0x180004506  call    ?SetHistoryAndEWR@CADMCOMW@@AEAAJKK@Z; CADMCOMW::SetHistoryAndEWR(ulong,ulong)
0x18000450b  mov     ebx, eax
0x18000450d  test    eax, eax
0x18000450f  js      short loc_18000451C
0x180004511  mov     eax, [rbp+57h+arg_18]
0x180004514  mov     [r14], eax
0x180004517  mov     eax, [rbp+57h+var_80]
0x18000451a  mov     [rsi], eax
0x18000451c  mov     edx, [rbp+57h+arg_8]
0x18000451f  test    edx, edx
0x180004521  jz      short loc_18000453D
0x180004523  mov     rcx, [rdi+20h]
0x180004527  mov     rax, [rcx]
0x18000452a  mov     rax, [rax+120h]
0x180004531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004536  jmp     short loc_18000453D
0x180004538  mov     ebx, 80070057h
0x18000453d  mov     eax, ebx
0x18000453f  mov     rbx, [rsp+0C0h+arg_0]
0x180004547  add     rsp, 0A0h
0x18000454e  pop     r15
0x180004550  pop     r14
0x180004552  pop     rdi
0x180004553  pop     rsi
0x180004554  pop     rbp
0x180004555  retn
```
