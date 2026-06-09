# NpSetAttribute

- ea: `0x14000b84c`
- end: `0x14000bac5`
- name: `NpSetAttribute`
- size: `633`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000efb0`

## callees

- `0x14000b768`
- `0x14000b84c`
- `0x140013ec0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b922`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b9c6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ba28`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b922`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b9c6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ba28`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ba93`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ba93`
- `ntoskrnl!_stricmp` at `0x14000b966`
- `ntoskrnl!_stricmp` at `0x14000b984`
- `ntoskrnl!_stricmp` at `0x14000b9a2`
- `ntoskrnl!_stricmp` at `0x14000b9e6`
- `ntoskrnl!_stricmp` at `0x14000ba04`
- `ntoskrnl!_stricmp` at `0x14000b966`
- `ntoskrnl!_stricmp` at `0x14000b984`
- `ntoskrnl!_stricmp` at `0x14000b9a2`
- `ntoskrnl!_stricmp` at `0x14000b9e6`
- `ntoskrnl!_stricmp` at `0x14000ba04`

## string_xrefs

- `0x14000b9dc`: `ServerProcessId`
- `0x14000b95c`: `ClientComputerName`
- `0x14000b97a`: `ClientProcessId`

## pseudocode

```c
__int64 __fastcall NpSetAttribute(_QWORD *a1, int a2)
{
  __int64 v2; // r13
  __int64 v5; // r8
  const char *v6; // rbp
  __int64 v7; // r9
  __int64 v8; // r9
  const char *v9; // r15
  __int64 v10; // r13
  unsigned __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rbx
  unsigned __int64 v14; // rbx
  int v15; // esi
  unsigned __int64 v16; // rsi
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned __int64 v21; // rcx
  __int64 v23; // [rsp+70h] [rbp+8h]
  __int64 v24; // [rsp+80h] [rbp+18h]

  v2 = a1[23];
  v5 = *(unsigned int *)(v2 + 16);
  if ( (_DWORD)v5 )
  {
    v6 = (const char *)a1[3];
    v7 = 0;
    do
    {
      if ( !v6[v7] )
        break;
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < (unsigned int)v5 );
    if ( (_DWORD)v7 && (_DWORD)v7 != (_DWORD)v5 )
    {
      v8 = (unsigned int)(v7 + 1);
      if ( (unsigned int)v8 >= (unsigned int)v5 )
      {
        v9 = 0;
        v23 = 0;
      }
      else
      {
        v9 = &v6[(unsigned int)v8];
        v5 = (unsigned int)(v5 - v8);
        v23 = (unsigned int)v5;
      }
      v10 = *(_QWORD *)(v2 + 48);
      if ( **(_WORD **)(v10 + 24) == 514 )
      {
        v11 = *(_QWORD *)(v10 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
        v12 = (*(_QWORD *)(v10 + 32) >> 1) & 1LL;
        v13 = *(_QWORD *)(v11 + 40);
        v24 = v13;
        if ( a2 )
        {
          if ( a2 != 1 )
          {
            if ( a2 == 2 )
            {
              v14 = v11 + 64;
              ExAcquirePushLockExclusiveEx(v11 + 64, 0, v5, v8);
              if ( !(_DWORD)v12 && (*(_QWORD *)(v10 + 32) & 1) == 0 )
              {
                v15 = -1073741648;
                goto LABEL_33;
              }
              v16 = v11 + 16 * (v12 + 20);
LABEL_27:
              if ( v9 )
              {
                v15 = NpSetAttributeInList(v16, 0, v6, v9, v23);
                if ( v15 < 0 )
                {
LABEL_31:
                  if ( !a2 )
                  {
                    v21 = v24 + 128;
                    goto LABEL_35;
                  }
                  if ( (unsigned int)(a2 - 1) > 1 )
                    return (unsigned int)v15;
LABEL_33:
                  v21 = v14;
LABEL_35:
                  ExReleasePushLockExclusiveEx(v21, 0);
                  return (unsigned int)v15;
                }
              }
              else
              {
                NpRemoveAttributeFromList(v16, v6);
                v15 = 0;
              }
              a1[7] = 0;
              goto LABEL_31;
            }
            return 3221225485LL;
          }
          if ( (_DWORD)v12
            && _stricmp(v6, "ClientComputerName")
            && _stricmp(v6, "ClientProcessId")
            && _stricmp(v6, "ClientSessionId") )
          {
            v14 = v11 + 64;
            v16 = v11 + 304;
            ExAcquirePushLockExclusiveEx(v11 + 64, 0, v17, v18);
            goto LABEL_27;
          }
        }
        else if ( (_DWORD)v12 && _stricmp(v6, "ServerProcessId") && _stricmp(v6, "ServerSessionId") )
        {
          v16 = v13 + 296;
          ExAcquirePushLockExclusiveEx(v13 + 128, 0, v19, v20);
          v14 = v11 + 64;
          goto LABEL_27;
        }
        return 3221225506LL;
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14000b84c  mov     [rsp+arg_8], rbx
0x14000b851  push    rbp
0x14000b852  push    rsi
0x14000b853  push    rdi
0x14000b854  push    r12
0x14000b856  push    r13
0x14000b858  push    r14
0x14000b85a  push    r15
0x14000b85c  sub     rsp, 30h
0x14000b860  mov     r13, [rcx+0B8h]
0x14000b867  mov     edi, edx
0x14000b869  mov     r12, rcx
0x14000b86c  mov     r8d, [r13+10h]
0x14000b870  test    r8d, r8d
0x14000b873  jz      loc_14000BAAA
0x14000b879  mov     rbp, [rcx+18h]
0x14000b87d  xor     r9d, r9d
0x14000b880  test    r8d, r8d
0x14000b883  jz      loc_14000BAAA
0x14000b889  cmp     byte ptr [r9+rbp], 0
0x14000b88e  jz      short loc_14000B898
0x14000b890  inc     r9d
0x14000b893  cmp     r9d, r8d
0x14000b896  jb      short loc_14000B889
0x14000b898  test    r9d, r9d
0x14000b89b  jz      loc_14000BAAA
0x14000b8a1  cmp     r9d, r8d
0x14000b8a4  jz      loc_14000BAAA
0x14000b8aa  inc     r9d
0x14000b8ad  cmp     r9d, r8d
0x14000b8b0  jnb     short loc_14000B8C5
0x14000b8b2  mov     r15d, r9d
0x14000b8b5  add     r15, rbp
0x14000b8b8  sub     r8d, r9d
0x14000b8bb  mov     ecx, r8d
0x14000b8be  mov     [rsp+68h+arg_0], rcx
0x14000b8c3  jmp     short loc_14000B8CD
0x14000b8c5  xor     r15d, r15d
0x14000b8c8  mov     [rsp+68h+arg_0], r15
0x14000b8cd  mov     r13, [r13+30h]
0x14000b8d1  mov     ecx, 202h
0x14000b8d6  mov     rax, [r13+18h]
0x14000b8da  cmp     [rax], cx
0x14000b8dd  jnz     loc_14000BAAA
0x14000b8e3  mov     rsi, [r13+20h]
0x14000b8e7  mov     ecx, edi
0x14000b8e9  mov     r14, [r13+20h]
0x14000b8ed  and     r14, 0FFFFFFFFFFFFFFFCh
0x14000b8f1  shr     rsi, 1
0x14000b8f4  and     esi, 1
0x14000b8f7  mov     rbx, [r14+28h]
0x14000b8fb  mov     [rsp+68h+arg_10], rbx
0x14000b903  test    edi, edi
0x14000b905  jz      loc_14000B9D4
0x14000b90b  sub     ecx, 1
0x14000b90e  jz      short loc_14000B954
0x14000b910  cmp     ecx, 1
0x14000b913  jnz     loc_14000BAAA
0x14000b919  lea     rbx, [r14+40h]
0x14000b91d  xor     edx, edx
0x14000b91f  mov     rcx, rbx
0x14000b922  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b929  nop     dword ptr [rax+rax+00h]
0x14000b92e  test    esi, esi
0x14000b930  jnz     short loc_14000B944
0x14000b932  mov     rax, [r13+20h]
0x14000b936  test    al, 1
0x14000b938  jnz     short loc_14000B944
0x14000b93a  mov     esi, 0C00000B0h
0x14000b93f  jmp     loc_14000BA80
0x14000b944  add     rsi, 14h
0x14000b948  shl     rsi, 4
0x14000b94c  add     rsi, r14
0x14000b94f  jmp     loc_14000BA38
0x14000b954  test    esi, esi
0x14000b956  jz      loc_14000BAA3
0x14000b95c  lea     rdx, Str2; "ClientComputerName"
0x14000b963  mov     rcx, rbp; Str1
0x14000b966  call    cs:__imp__stricmp
0x14000b96d  nop     dword ptr [rax+rax+00h]
0x14000b972  test    eax, eax
0x14000b974  jz      loc_14000BAA3
0x14000b97a  lea     rdx, aClientprocessi; "ClientProcessId"
0x14000b981  mov     rcx, rbp; Str1
0x14000b984  call    cs:__imp__stricmp
0x14000b98b  nop     dword ptr [rax+rax+00h]
0x14000b990  test    eax, eax
0x14000b992  jz      loc_14000BAA3
0x14000b998  lea     rdx, aClientsessioni; "ClientSessionId"
0x14000b99f  mov     rcx, rbp; Str1
0x14000b9a2  call    cs:__imp__stricmp
0x14000b9a9  nop     dword ptr [rax+rax+00h]
0x14000b9ae  test    eax, eax
0x14000b9b0  jz      loc_14000BAA3
0x14000b9b6  lea     rbx, [r14+40h]
0x14000b9ba  xor     edx, edx
0x14000b9bc  mov     rcx, rbx
0x14000b9bf  lea     rsi, [r14+130h]
0x14000b9c6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b9cd  nop     dword ptr [rax+rax+00h]
0x14000b9d2  jmp     short loc_14000BA38
0x14000b9d4  test    esi, esi
0x14000b9d6  jz      loc_14000BAA3
0x14000b9dc  lea     rdx, aServerprocessi; "ServerProcessId"
0x14000b9e3  mov     rcx, rbp; Str1
0x14000b9e6  call    cs:__imp__stricmp
0x14000b9ed  nop     dword ptr [rax+rax+00h]
0x14000b9f2  test    eax, eax
0x14000b9f4  jz      loc_14000BAA3
0x14000b9fa  lea     rdx, aServersessioni; "ServerSessionId"
0x14000ba01  mov     rcx, rbp; Str1
0x14000ba04  call    cs:__imp__stricmp
0x14000ba0b  nop     dword ptr [rax+rax+00h]
0x14000ba10  test    eax, eax
0x14000ba12  jz      loc_14000BAA3
0x14000ba18  lea     rcx, [rbx+80h]
0x14000ba1f  xor     edx, edx
0x14000ba21  lea     rsi, [rbx+128h]
0x14000ba28  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ba2f  nop     dword ptr [rax+rax+00h]
0x14000ba34  lea     rbx, [r14+40h]
0x14000ba38  mov     rcx, rsi
0x14000ba3b  test    r15, r15
0x14000ba3e  jnz     short loc_14000BA4C
0x14000ba40  mov     rdx, rbp
0x14000ba43  call    NpRemoveAttributeFromList
0x14000ba48  xor     esi, esi
0x14000ba4a  jmp     short loc_14000BA69
0x14000ba4c  mov     rax, [rsp+68h+arg_0]
0x14000ba51  mov     r9, r15
0x14000ba54  mov     r8, rbp
0x14000ba57  mov     [rsp+68h+var_48], rax
0x14000ba5c  xor     edx, edx
0x14000ba5e  call    NpSetAttributeInList
0x14000ba63  mov     esi, eax
0x14000ba65  test    eax, eax
0x14000ba67  js      short loc_14000BA72
0x14000ba69  mov     qword ptr [r12+38h], 0
0x14000ba72  test    edi, edi
0x14000ba74  jz      short loc_14000BA85
0x14000ba76  sub     edi, 1
0x14000ba79  jz      short loc_14000BA80
0x14000ba7b  cmp     edi, 1
0x14000ba7e  jnz     short loc_14000BA9F
0x14000ba80  mov     rcx, rbx
0x14000ba83  jmp     short loc_14000BA91
0x14000ba85  mov     rcx, [rsp+68h+arg_10]
0x14000ba8d  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000ba91  xor     edx, edx
0x14000ba93  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ba9a  nop     dword ptr [rax+rax+00h]
0x14000ba9f  mov     eax, esi
0x14000baa1  jmp     short loc_14000BAAF
0x14000baa3  mov     eax, 0C0000022h
0x14000baa8  jmp     short loc_14000BAAF
0x14000baaa  mov     eax, 0C000000Dh
0x14000baaf  mov     rbx, [rsp+68h+arg_8]
0x14000bab4  add     rsp, 30h
0x14000bab8  pop     r15
0x14000baba  pop     r14
0x14000babc  pop     r13
0x14000babe  pop     r12
0x14000bac0  pop     rdi
0x14000bac1  pop     rsi
0x14000bac2  pop     rbp
0x14000bac3  retn
```
