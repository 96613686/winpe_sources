# NpGetAttribute

- ea: `0x1400104c0`
- end: `0x140010705`
- name: `NpGetAttribute`
- size: `581`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000efb0`

## callees

- `0x140001f40`
- `0x1400104c0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400105ac`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400105ac`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001054b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140010585`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400105d6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001054b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140010585`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400105d6`

## string_xrefs

- `0x140010630`: `ServerProcessId`
- `0x140010642`: `ClientComputerName`
- `0x14001064b`: `ClientProcessId`
- `0x14001065d`: `RestrictedAccess`

## pseudocode

```c
__int64 __fastcall NpGetAttribute(_QWORD *a1, int a2)
{
  __int64 v2; // r9
  int v5; // eax
  _BYTE *v6; // r15
  __int64 v7; // rbx
  unsigned __int64 v8; // rbp
  __int64 v9; // rdi
  __int64 v10; // r12
  unsigned int v11; // ebx
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rsi
  _QWORD *v15; // r9
  bool v16; // zf
  const char *v17; // rdx
  signed __int64 v18; // r8
  int v19; // eax
  int v20; // ecx
  unsigned __int64 v21; // rdi
  _QWORD *v22; // rdx
  unsigned int v23; // [rsp+70h] [rbp+8h]

  v2 = a1[23];
  v5 = *(_DWORD *)(v2 + 16);
  if ( !v5 )
    return 3221225485LL;
  v6 = (_BYTE *)a1[3];
  if ( v6[v5 - 1] )
    return 3221225485LL;
  v7 = *(_QWORD *)(v2 + 48);
  if ( **(_WORD **)(v7 + 24) != 514 )
    return 3221225485LL;
  v8 = *(_QWORD *)(v7 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
  v9 = (*(_QWORD *)(v7 + 32) >> 1) & 1LL;
  v23 = *(_DWORD *)(v2 + 8);
  v10 = *(_QWORD *)(v8 + 40);
  switch ( a2 )
  {
    case 1:
      v13 = (_QWORD *)(v8 + 304);
      ExAcquirePushLockSharedEx(v8 + 64, 0);
      if ( !(_DWORD)v9 && (*(_QWORD *)(v7 + 32) & 1) == 0 )
        goto LABEL_9;
      goto LABEL_20;
    case 0:
      ExAcquirePushLockSharedEx(v10 + 128, 0);
      if ( !(_DWORD)v9 && (*(_QWORD *)(v7 + 32) & 1) == 0 )
      {
        v11 = -1073741648;
        goto LABEL_14;
      }
      v13 = (_QWORD *)(v10 + 296);
LABEL_20:
      v15 = (_QWORD *)*v13;
      if ( (_QWORD *)*v13 == v13 )
      {
LABEL_36:
        v11 = -1073741275;
      }
      else
      {
        while ( 1 )
        {
          if ( (unsigned __int64)v6 >= 8 )
          {
            v17 = (const char *)v15[2];
            switch ( (int)v17 )
            {
              case 1:
                v17 = "ServerProcessId";
                break;
              case 2:
                v17 = "ServerSessionId";
                break;
              case 3:
                v17 = "ClientProcessId";
                break;
              case 4:
                v17 = "ClientSessionId";
                break;
              case 6:
                v17 = "ClientComputerName";
                break;
              case 7:
                v17 = "RestrictedAccess";
                break;
              default:
                break;
            }
            v18 = v6 - v17;
            do
            {
              v19 = (unsigned __int8)v17[v18];
              v20 = *(unsigned __int8 *)v17 - v19;
              if ( v20 )
                break;
              ++v17;
            }
            while ( v19 );
            v16 = v20 == 0;
          }
          else
          {
            v16 = v15[2] == (_QWORD)v6;
          }
          if ( v16 )
            break;
          v15 = (_QWORD *)*v15;
          if ( v15 == v13 )
            goto LABEL_36;
        }
        v21 = v15[3];
        v22 = v15 + 4;
        if ( v21 > 8 )
          v22 = (_QWORD *)*v22;
        if ( v21 <= v23 )
        {
          v11 = 0;
          memmove(v6, v22, v15[3]);
          a1[7] = v21;
        }
        else
        {
          v11 = -1073741789;
        }
      }
      if ( a2 )
      {
        if ( (unsigned int)(a2 - 1) > 1 )
          return v11;
        v12 = v8 + 64;
LABEL_15:
        ExReleasePushLockSharedEx(v12, 0);
        return v11;
      }
LABEL_14:
      v12 = v10 + 128;
      goto LABEL_15;
    case 2:
      ExAcquirePushLockSharedEx(v8 + 64, 0);
      if ( !(_DWORD)v9 && (*(_QWORD *)(v7 + 32) & 1) == 0 )
      {
LABEL_9:
        v11 = -1073741648;
        v12 = v8 + 64;
        goto LABEL_15;
      }
      v13 = (_QWORD *)(v8 + 16 * (v9 + 20));
      goto LABEL_20;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400104c0  push    rbx
0x1400104c2  push    rbp
0x1400104c3  push    rsi
0x1400104c4  push    rdi
0x1400104c5  push    r12
0x1400104c7  push    r13
0x1400104c9  push    r14
0x1400104cb  push    r15
0x1400104cd  sub     rsp, 28h
0x1400104d1  mov     r9, [rcx+0B8h]
0x1400104d8  mov     r14d, edx
0x1400104db  mov     r13, rcx
0x1400104de  mov     eax, [r9+10h]
0x1400104e2  test    eax, eax
0x1400104e4  jz      loc_1400106EE
0x1400104ea  mov     r15, [rcx+18h]
0x1400104ee  dec     eax
0x1400104f0  cmp     byte ptr [rax+r15], 0
0x1400104f5  jnz     loc_1400106EE
0x1400104fb  mov     rbx, [r9+30h]
0x1400104ff  mov     ecx, 202h
0x140010504  mov     rax, [rbx+18h]
0x140010508  cmp     [rax], cx
0x14001050b  jnz     loc_1400106EE
0x140010511  mov     rdi, [rbx+20h]
0x140010515  mov     rbp, [rbx+20h]
0x140010519  mov     eax, [r9+8]
0x14001051d  and     rbp, 0FFFFFFFFFFFFFFFCh
0x140010521  shr     rdi, 1
0x140010524  and     edi, 1
0x140010527  mov     [rsp+68h+arg_0], eax
0x14001052b  mov     r12, [rbp+28h]
0x14001052f  cmp     edx, 1
0x140010532  jz      loc_1400105C9
0x140010538  test    edx, edx
0x14001053a  jz      short loc_14001057B
0x14001053c  cmp     edx, 2
0x14001053f  jnz     loc_1400106EE
0x140010545  lea     rcx, [rbp+40h]
0x140010549  xor     edx, edx
0x14001054b  call    cs:__imp_ExAcquirePushLockSharedEx
0x140010552  nop     dword ptr [rax+rax+00h]
0x140010557  test    edi, edi
0x140010559  jnz     short loc_14001056E
0x14001055b  mov     rax, [rbx+20h]
0x14001055f  test    al, 1
0x140010561  jnz     short loc_14001056E
0x140010563  mov     ebx, 0C00000B0h
0x140010568  lea     rcx, [rbp+40h]
0x14001056c  jmp     short loc_1400105AA
0x14001056e  lea     rsi, [rdi+14h]
0x140010572  shl     rsi, 4
0x140010576  add     rsi, rbp
0x140010579  jmp     short loc_1400105F2
0x14001057b  lea     rcx, [r12+80h]
0x140010583  xor     edx, edx
0x140010585  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001058c  nop     dword ptr [rax+rax+00h]
0x140010591  test    edi, edi
0x140010593  jnz     short loc_1400105BF
0x140010595  mov     rax, [rbx+20h]
0x140010599  test    al, 1
0x14001059b  jnz     short loc_1400105BF
0x14001059d  mov     ebx, 0C00000B0h
0x1400105a2  lea     rcx, [r12+80h]
0x1400105aa  xor     edx, edx
0x1400105ac  call    cs:__imp_ExReleasePushLockSharedEx
0x1400105b3  nop     dword ptr [rax+rax+00h]
0x1400105b8  mov     eax, ebx
0x1400105ba  jmp     loc_1400106F3
0x1400105bf  lea     rsi, [r12+128h]
0x1400105c7  jmp     short loc_1400105F2
0x1400105c9  lea     rcx, [rbp+40h]
0x1400105cd  xor     edx, edx
0x1400105cf  lea     rsi, [rbp+130h]
0x1400105d6  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400105dd  nop     dword ptr [rax+rax+00h]
0x1400105e2  test    edi, edi
0x1400105e4  jnz     short loc_1400105F2
0x1400105e6  mov     rax, [rbx+20h]
0x1400105ea  test    al, 1
0x1400105ec  jz      loc_140010563
0x1400105f2  mov     r9, [rsi]
0x1400105f5  cmp     r9, rsi
0x1400105f8  jz      loc_140010693
0x1400105fe  lea     r10, cs:140000000h
0x140010605  cmp     r15, 8
0x140010609  jnb     short loc_140010611
0x14001060b  cmp     [r9+10h], r15
0x14001060f  jmp     short loc_140010685
0x140010611  mov     rdx, [r9+10h]
0x140010615  lea     eax, [rdx-1]; switch 7 cases
0x140010618  cmp     eax, 6
0x14001061b  ja      short def_14001062A; jumptable 000000014001062A default case, case 5
0x14001061d  cdqe
0x14001061f  mov     ecx, ds:(jpt_14001062A - 140000000h)[r10+rax*4]
0x140010627  add     rcx, r10
0x14001062a  jmp     rcx; switch jump
0x140010630  lea     rdx, aServerprocessi; jumptable 000000014001062A case 1
0x140010637  jmp     short def_14001062A; jumptable 000000014001062A default case, case 5
0x140010639  lea     rdx, aServersessioni; jumptable 000000014001062A case 2
0x140010640  jmp     short def_14001062A; jumptable 000000014001062A default case, case 5
0x140010642  lea     rdx, Str2; jumptable 000000014001062A case 6
0x140010649  jmp     short def_14001062A; jumptable 000000014001062A default case, case 5
0x14001064b  lea     rdx, aClientprocessi; jumptable 000000014001062A case 3
0x140010652  jmp     short def_14001062A; jumptable 000000014001062A default case, case 5
0x140010654  lea     rdx, aClientsessioni; jumptable 000000014001062A case 4
0x14001065b  jmp     short def_14001062A; jumptable 000000014001062A default case, case 5
0x14001065d  lea     rdx, aRestrictedacce; jumptable 000000014001062A case 7
0x140010664  mov     r8, r15; jumptable 000000014001062A default case, case 5
0x140010667  sub     r8, rdx
0x14001066a  nop     word ptr [rax+rax+00h]
0x140010670  movzx   ecx, byte ptr [rdx]
0x140010673  movzx   eax, byte ptr [rdx+r8]
0x140010678  sub     ecx, eax
0x14001067a  jnz     short loc_140010683
0x14001067c  inc     rdx
0x14001067f  test    eax, eax
0x140010681  jnz     short loc_140010670
0x140010683  test    ecx, ecx
0x140010685  jz      short loc_1400106BA
0x140010687  mov     r9, [r9]
0x14001068a  cmp     r9, rsi
0x14001068d  jnz     loc_140010605
0x140010693  mov     ebx, 0C0000225h
0x140010698  test    r14d, r14d
0x14001069b  jz      loc_1400105A2
0x1400106a1  sub     r14d, 1
0x1400106a5  jz      short loc_1400106B1
0x1400106a7  cmp     r14d, 1
0x1400106ab  jnz     loc_1400105B8
0x1400106b1  lea     rcx, [rbp+40h]
0x1400106b5  jmp     loc_1400105AA
0x1400106ba  mov     rdi, [r9+18h]
0x1400106be  lea     rdx, [r9+20h]
0x1400106c2  cmp     rdi, 8
0x1400106c6  jbe     short loc_1400106CB
0x1400106c8  mov     rdx, [rdx]; Src
0x1400106cb  mov     eax, [rsp+68h+arg_0]
0x1400106cf  cmp     rdi, rax
0x1400106d2  jbe     short loc_1400106DB
0x1400106d4  mov     ebx, 0C0000023h
0x1400106d9  jmp     short loc_140010698
0x1400106db  xor     ebx, ebx
0x1400106dd  mov     r8, rdi; Size
0x1400106e0  mov     rcx, r15; void *
0x1400106e3  call    memmove
0x1400106e8  mov     [r13+38h], rdi
0x1400106ec  jmp     short loc_140010698
0x1400106ee  mov     eax, 0C000000Dh
0x1400106f3  add     rsp, 28h
0x1400106f7  pop     r15
0x1400106f9  pop     r14
0x1400106fb  pop     r13
0x1400106fd  pop     r12
0x1400106ff  pop     rdi
0x140010700  pop     rsi
0x140010701  pop     rbp
0x140010702  pop     rbx
0x140010703  retn
```
