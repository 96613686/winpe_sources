# SdpVerifySequenceOf

- ea: `0x14003573c`
- end: `0x1400358ef`
- name: `SdpVerifySequenceOf`
- size: `435`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140035260`
- `0x1400352d4`
- `0x140035430`
- `0x1400354c0`
- `0x1400358f8`

## callees

- `0x14001fc70`
- `0x14003573c`
- `0x140036444`
- `0x1400365d0`

## pseudocode

```c
__int64 __fastcall SdpVerifySequenceOf(
        _BYTE *a1,
        __int64 a2,
        char a3,
        _BYTE *a4,
        _DWORD *a5,
        __int64 (__fastcall *a6)(__int64, __int64, __int64, __int64),
        __int64 a7)
{
  __int64 v7; // r14
  char v9; // si
  int v10; // edi
  __int64 v11; // rdx
  _BYTE *v12; // rbx
  _DWORD *v13; // r13
  char v14; // r15
  __int64 v15; // r10
  __int64 v16; // r8
  __int64 result; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-1Ch] BYREF
  int v22; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+98h] [rbp+48h] BYREF
  char v25; // [rsp+A0h] [rbp+50h]

  v25 = a3;
  v7 = (unsigned int)a2;
  v21 = 0;
  v24 = 0;
  v9 = a3;
  v20 = 0;
  v10 = (int)a1;
  v23[0] = 0;
  v22 = 0;
  if ( (_DWORD)a2 )
  {
    if ( (*a1 & 0xF8) == 0x30 )
    {
      LOBYTE(a2) = *a1 & 7;
      SdpRetrieveVariableSize(a1 + 1, a2, &v21, &v24);
      if ( v7 == v24 + v21 + 1LL )
      {
        SdpGetNextElement(v10, v7, 0, (unsigned int)v23, (__int64)&v22);
        v12 = (_BYTE *)v23[0];
        if ( !v23[0] )
          return 0;
        v13 = a5;
        while ( 1 )
        {
          v14 = *v12 >> 3;
          if ( v14 != v9 )
            break;
          LOBYTE(v11) = *v12 & 7;
          if ( a4 )
          {
            if ( (unsigned __int8)v11 > 4u || !*a4 )
              return 3221225485LL;
            v15 = (unsigned __int8)v11;
            v16 = 0;
            while ( g_IndexToDataSize[(unsigned __int8)v11] != (unsigned __int8)a4[v16] )
            {
              v16 = (unsigned int)(v16 + 1);
              if ( !a4[v16] )
                return 3221225485LL;
            }
          }
          else
          {
            v15 = (unsigned __int8)v11;
          }
          if ( v13 )
            ++*v13;
          if ( a6 )
          {
            if ( (unsigned __int8)v11 < 5u )
            {
              v18 = (unsigned int)g_IndexToDataSize[v15];
              v19 = (__int64)(v12 + 1);
              v20 = g_IndexToDataSize[v15];
            }
            else
            {
              SdpRetrieveVariableSize(v12 + 1, v11, &v20, &v24);
              v18 = v20;
              v19 = (__int64)&v12[v24 + 1];
            }
            LOBYTE(v11) = v14;
            result = a6(a7, v11, v18, v19);
            if ( (int)(result + 0x80000000) >= 0 && (_DWORD)result != -1073741184 )
              return result;
            v9 = v25;
          }
          SdpGetNextElement(v10, v7, (_DWORD)v12, (unsigned int)v23, (__int64)&v22);
          v12 = (_BYTE *)v23[0];
          if ( !v23[0] )
            return 0;
        }
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14003573c  mov     [rsp-38h+arg_0], rbx
0x140035741  mov     [rsp-38h+arg_10], r8b
0x140035746  push    rbp
0x140035747  push    rsi
0x140035748  push    rdi
0x140035749  push    r12
0x14003574b  push    r13
0x14003574d  push    r14
0x14003574f  push    r15
0x140035751  mov     rbp, rsp
0x140035754  sub     rsp, 50h
0x140035758  xor     r15d, r15d
0x14003575b  mov     r14d, edx
0x14003575e  mov     [rbp+var_1C], r15d
0x140035762  mov     r12, r9
0x140035765  mov     [rbp+arg_8], r15d
0x140035769  mov     sil, r8b
0x14003576c  mov     [rbp+var_20], r15d
0x140035770  mov     rdi, rcx
0x140035773  mov     [rbp+var_10], r15
0x140035777  mov     [rbp+var_18], r15d
0x14003577b  test    edx, edx
0x14003577d  jz      loc_140035829
0x140035783  mov     dl, [rcx]
0x140035785  mov     al, dl
0x140035787  and     al, 0F8h
0x140035789  cmp     al, 30h ; '0'
0x14003578b  jnz     loc_140035829
0x140035791  and     dl, 7
0x140035794  lea     r9, [rbp+arg_8]
0x140035798  inc     rcx
0x14003579b  lea     r8, [rbp+var_1C]
0x14003579f  call    SdpRetrieveVariableSize
0x1400357a4  mov     ecx, [rbp+var_1C]
0x1400357a7  mov     edx, [rbp+arg_8]
0x1400357aa  inc     rcx
0x1400357ad  add     rcx, rdx
0x1400357b0  cmp     r14, rcx
0x1400357b3  jnz     short loc_140035829
0x1400357b5  lea     rax, [rbp+var_18]
0x1400357b9  xor     r8d, r8d
0x1400357bc  lea     r9, [rbp+var_10]
0x1400357c0  mov     [rsp+50h+var_30], rax
0x1400357c5  mov     edx, r14d
0x1400357c8  mov     rcx, rdi
0x1400357cb  call    SdpGetNextElement
0x1400357d0  mov     rbx, [rbp+var_10]
0x1400357d4  test    rbx, rbx
0x1400357d7  jz      loc_1400358E8
0x1400357dd  mov     r13, [rbp+arg_20]
0x1400357e1  mov     dl, [rbx]
0x1400357e3  lea     rax, g_IndexToDataSize
0x1400357ea  mov     r15b, dl
0x1400357ed  shr     r15b, 3
0x1400357f1  cmp     r15b, sil
0x1400357f4  jnz     short loc_140035829
0x1400357f6  and     dl, 7
0x1400357f9  test    r12, r12
0x1400357fc  jz      short loc_140035850
0x1400357fe  cmp     dl, 4
0x140035801  ja      short loc_140035829
0x140035803  cmp     byte ptr [r12], 0
0x140035808  jz      short loc_140035829
0x14003580a  movzx   r10d, dl
0x14003580e  xor     r8d, r8d
0x140035811  mov     r9d, [rax+r10*4]
0x140035815  movzx   ecx, byte ptr [r8+r12]
0x14003581a  cmp     r9d, ecx
0x14003581d  jz      short loc_140035847
0x14003581f  inc     r8d
0x140035822  cmp     byte ptr [r8+r12], 0
0x140035827  jnz     short loc_140035815
0x140035829  mov     eax, 0C000000Dh
0x14003582e  mov     rbx, [rsp+50h+arg_0]
0x140035836  add     rsp, 50h
0x14003583a  pop     r15
0x14003583c  pop     r14
0x14003583e  pop     r13
0x140035840  pop     r12
0x140035842  pop     rdi
0x140035843  pop     rsi
0x140035844  pop     rbp
0x140035845  retn
0x140035847  lea     rax, g_IndexToDataSize
0x14003584e  jmp     short loc_140035854
0x140035850  movzx   r10d, dl
0x140035854  test    r13, r13
0x140035857  jz      short loc_14003585D
0x140035859  inc     dword ptr [r13+0]
0x14003585d  cmp     [rbp+arg_28], 0
0x140035862  jz      short loc_1400358C0
0x140035864  lea     rsi, [rbx+1]
0x140035868  cmp     dl, 5
0x14003586b  jb      short loc_14003588A
0x14003586d  lea     r9, [rbp+arg_8]
0x140035871  mov     rcx, rsi
0x140035874  lea     r8, [rbp+var_20]
0x140035878  call    SdpRetrieveVariableSize
0x14003587d  mov     r9d, [rbp+arg_8]
0x140035881  mov     r8d, [rbp+var_20]
0x140035885  add     r9, rsi
0x140035888  jmp     short loc_140035895
0x14003588a  mov     r8d, [rax+r10*4]
0x14003588e  mov     r9, rsi
0x140035891  mov     [rbp+var_20], r8d
0x140035895  mov     rcx, [rbp+arg_30]
0x140035899  mov     dl, r15b
0x14003589c  mov     rax, [rbp+arg_28]
0x1400358a0  call    _guard_dispatch_icall
0x1400358a5  mov     edx, 80000000h
0x1400358aa  lea     ecx, [rax+rdx]
0x1400358ad  test    edx, ecx
0x1400358af  jnz     short loc_1400358BC
0x1400358b1  cmp     eax, 0C0000280h
0x1400358b6  jnz     loc_14003582E
0x1400358bc  mov     sil, [rbp+arg_10]
0x1400358c0  lea     rax, [rbp+var_18]
0x1400358c4  mov     r8, rbx
0x1400358c7  lea     r9, [rbp+var_10]
0x1400358cb  mov     [rsp+50h+var_30], rax
0x1400358d0  mov     edx, r14d
0x1400358d3  mov     rcx, rdi
0x1400358d6  call    SdpGetNextElement
0x1400358db  mov     rbx, [rbp+var_10]
0x1400358df  test    rbx, rbx
0x1400358e2  jnz     loc_1400357E1
0x1400358e8  xor     eax, eax
0x1400358ea  jmp     loc_14003582E
```
