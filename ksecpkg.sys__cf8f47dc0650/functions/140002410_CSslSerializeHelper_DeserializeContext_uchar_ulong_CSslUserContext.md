# CSslSerializeHelper::DeserializeContext(uchar *,ulong,CSslUserContext * *)

- ea: `0x140002410`
- end: `0x1400024fb`
- name: `?DeserializeContext@CSslSerializeHelper@@QEAAJPEAEKPEAPEAUCSslUserContext@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(CSslSerializeHelper *__hidden this, unsigned __int8 *, unsigned int, struct CSslUserContext **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400230a0`

## callees

- `0x140002410`
- `0x140002510`
- `0x140002c20`
- `0x1400045b0`

## pseudocode

```c
__int64 __fastcall CSslSerializeHelper::DeserializeContext(
        CSslSerializeHelper *this,
        unsigned __int8 *a2,
        int a3,
        struct CSslUserContext **a4)
{
  unsigned int v4; // r11d
  unsigned __int8 *v5; // r10
  unsigned int v8; // r8d
  unsigned int v9; // r9d
  int v10; // eax
  unsigned int v11; // ebx
  struct CSslUserContext *UserContext; // rax
  __int64 result; // rax

  v4 = 0;
  v5 = &a2[a3];
  *a4 = 0;
  *((_QWORD *)this + 1) = a2;
  *((_DWORD *)this + 6) = a3;
  while ( 1 )
  {
LABEL_2:
    if ( a2 + 16 > v5 || (v8 = *((_DWORD *)a2 + 1), v9 = *((_DWORD *)a2 + 2), v9 > v8) )
    {
LABEL_11:
      v11 = -2146893052;
LABEL_16:
      if ( *a4 )
        DeleteUserContext(*a4);
      return v11;
    }
    v10 = *(_DWORD *)a2;
    if ( *(_DWORD *)a2 != 17 )
      break;
LABEL_7:
    v4 += (v9 + 7) & 0xFFFFFFF8;
LABEL_8:
    a2 += v8 + 16;
  }
  if ( v10 == 18 )
    goto LABEL_8;
  switch ( v10 )
  {
    case 0:
      UserContext = CreateUserContext(v4);
      *a4 = UserContext;
      if ( !UserContext )
      {
        v11 = -2146893056;
        goto LABEL_16;
      }
      result = CSslSerializeHelper::DeserializeContextWorker(this, UserContext);
      v11 = result;
      if ( (_DWORD)result )
        goto LABEL_16;
      break;
    case 1:
      if ( v8 < 8 )
        goto LABEL_11;
      v4 = 528;
      a2 += v8 + 16;
      goto LABEL_2;
    case 2:
    case 3:
    case 19:
    case 20:
      goto LABEL_8;
    case 4:
    case 5:
    case 6:
    case 7:
    case 8:
    case 9:
    case 10:
    case 11:
    case 12:
    case 13:
    case 14:
    case 15:
    case 16:
    case 21:
      goto LABEL_7;
    default:
      goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x140002410  mov     [rsp+arg_0], rbx
0x140002415  mov     [rsp+arg_8], rsi
0x14000241a  push    rdi
0x14000241b  sub     rsp, 20h
0x14000241f  xor     r11d, r11d
0x140002422  mov     r10d, r8d
0x140002425  add     r10, rdx
0x140002428  mov     qword ptr [r9], 0
0x14000242f  mov     rdi, r9
0x140002432  mov     [rcx+8], rdx
0x140002436  mov     rbx, rcx
0x140002439  mov     [rcx+18h], r8d
0x14000243d  lea     rsi, cs:140000000h
0x140002444  lea     rax, [rdx+10h]
0x140002448  cmp     rax, r10
0x14000244b  ja      short def_14000247E; jumptable 000000014000247E default case, cases 17,18
0x14000244d  mov     r8d, [rdx+4]
0x140002451  mov     r9d, [rdx+8]
0x140002455  cmp     r9d, r8d
0x140002458  ja      short def_14000247E; jumptable 000000014000247E default case, cases 17,18
0x14000245a  movsxd  rax, dword ptr [rdx]
0x14000245d  cmp     eax, 11h
0x140002460  jz      short loc_140002484; jumptable 000000014000247E cases 4-16,21
0x140002462  cmp     eax, 12h
0x140002465  jz      short loc_14000248E; jumptable 000000014000247E cases 2,3,19,20
0x140002467  cmp     eax, 15h; switch 22 cases
0x14000246a  ja      short def_14000247E; jumptable 000000014000247E default case, cases 17,18
0x14000246c  movzx   eax, ds:(byte_140015456 - 140000000h)[rsi+rax]
0x140002474  mov     ecx, ds:(jpt_14000247E - 140000000h)[rsi+rax*4]
0x14000247b  add     rcx, rsi
0x14000247e  jmp     rcx; switch jump
0x140002484  lea     eax, [r9+7]; jumptable 000000014000247E cases 4-16,21
0x140002488  and     eax, 0FFFFFFF8h
0x14000248b  add     r11d, eax
0x14000248e  lea     ecx, [r8+10h]; jumptable 000000014000247E cases 2,3,19,20
0x140002492  add     rdx, rcx
0x140002495  jmp     short loc_140002444
0x140002497  cmp     r8d, 8; jumptable 000000014000247E case 1
0x14000249b  jb      short def_14000247E; jumptable 000000014000247E default case, cases 17,18
0x14000249d  lea     ecx, [r8+10h]
0x1400024a1  mov     r11d, 210h
0x1400024a7  add     rdx, rcx
0x1400024aa  jmp     short loc_140002444
0x1400024ac  mov     ebx, 80090304h; jumptable 000000014000247E default case, cases 17,18
0x1400024b1  jmp     short loc_1400024EA
0x1400024b3  mov     ecx, r11d; jumptable 000000014000247E case 0
0x1400024b6  call    ?CreateUserContext@@YAPEAUCSslUserContext@@K@Z; CreateUserContext(ulong)
0x1400024bb  mov     [rdi], rax
0x1400024be  test    rax, rax
0x1400024c1  jz      short loc_1400024E5
0x1400024c3  mov     rdx, rax; struct CSslUserContext *
0x1400024c6  mov     rcx, rbx; this
0x1400024c9  call    ?DeserializeContextWorker@CSslSerializeHelper@@AEAAJPEAUCSslUserContext@@K@Z; CSslSerializeHelper::DeserializeContextWorker(CSslUserContext *,ulong)
0x1400024ce  mov     ebx, eax
0x1400024d0  test    eax, eax
0x1400024d2  jnz     short loc_1400024EA
0x1400024d4  mov     rbx, [rsp+28h+arg_0]
0x1400024d9  mov     rsi, [rsp+28h+arg_8]
0x1400024de  add     rsp, 20h
0x1400024e2  pop     rdi
0x1400024e3  retn
0x1400024e5  mov     ebx, 80090300h
0x1400024ea  mov     rcx, [rdi]; Entry
0x1400024ed  test    rcx, rcx
0x1400024f0  jz      short loc_1400024F7
0x1400024f2  call    ?DeleteUserContext@@YAXPEAUCSslUserContext@@@Z; DeleteUserContext(CSslUserContext *)
0x1400024f7  mov     eax, ebx
0x1400024f9  jmp     short loc_1400024D4
```
