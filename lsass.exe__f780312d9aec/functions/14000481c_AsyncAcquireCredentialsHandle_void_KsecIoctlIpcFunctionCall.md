# AsyncAcquireCredentialsHandle(void *,_KsecIoctlIpcFunctionCall *)

- ea: `0x14000481c`
- end: `0x1400049c1`
- name: `?AsyncAcquireCredentialsHandle@@YAXPEAXPEAU_KsecIoctlIpcFunctionCall@@@Z`
- size: `421`
- prototype: `void __fastcall(void *, struct _KsecIoctlIpcFunctionCall *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x140004d80`

## callees

- `0x140001d10`
- `0x1400020c0`
- `0x14000481c`
- `0x140005044`

## import_xrefs

- `SspiSrv!SspirAcquireCredentialsHandle` at `0x14000496b`
- `SspiSrv!SspirAcquireCredentialsHandle` at `0x14000496b`

## pseudocode

```c
void __fastcall AsyncAcquireCredentialsHandle(void *a1, struct _KsecIoctlIpcFunctionCall *a2)
{
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  _DWORD *v10; // rcx
  bool v11; // zf
  int v12; // eax
  __int64 v13; // rdx
  __int64 InBuffer; // [rsp+70h] [rbp-38h] BYREF
  __int128 v15; // [rsp+78h] [rbp-30h] BYREF
  __int128 v16; // [rsp+88h] [rbp-20h] BYREF

  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 40) )
  {
    v13 = 3221225659LL;
    goto LABEL_20;
  }
  v4 = *((unsigned int *)a2 + 10);
  if ( (unsigned int)v4 < 0x78 )
    goto LABEL_18;
  v5 = (unsigned __int64)a2 + 64;
  v6 = *((_QWORD *)a2 + 9);
  if ( v4 < v6 )
    goto LABEL_18;
  if ( v6 )
  {
    *(_QWORD *)(v5 + 8) = (char *)a2 + v6;
    LODWORD(v4) = *((_DWORD *)a2 + 10);
  }
  v7 = *((_QWORD *)a2 + 7);
  if ( (unsigned int)v4 < v7 )
    goto LABEL_18;
  if ( v7 )
    *((_QWORD *)a2 + 7) = (char *)a2 + v7;
  v8 = *((_QWORD *)a2 + 14);
  if ( v8 )
  {
    if ( *((unsigned int *)a2 + 10) >= v8 )
    {
      *((_QWORD *)a2 + 14) = (char *)a2 + v8;
      goto LABEL_13;
    }
LABEL_18:
    v13 = 3221225507LL;
    goto LABEL_20;
  }
LABEL_13:
  v9 = *(_QWORD *)a2;
  v10 = (_DWORD *)((char *)a2 + 84);
  v11 = *((_DWORD *)a2 + 22) == 0;
  v15 = 0;
  InBuffer = v9;
  v16 = 0;
  if ( v11 && !*v10 )
    v10 = 0;
  LODWORD(v15) = ((__int64 (__fastcall *)(void *, char *, unsigned __int64, unsigned __int64, _DWORD, _DWORD *, char *, _QWORD, _QWORD, _DWORD, char *, char *, _QWORD, _QWORD, __int64, _QWORD))SspirAcquireCredentialsHandle)(
                   a1,
                   (char *)a2 + 16,
                   ((unsigned __int64)a2 + 48) & -(__int64)(*((_WORD *)a2 + 24) != 0),
                   v5 & -(__int64)(*(_WORD *)v5 != 0),
                   *((_DWORD *)a2 + 20),
                   v10,
                   (char *)a2 + 96,
                   0,
                   0,
                   0,
                   (char *)&v15 + 8,
                   (char *)&v16 + 8,
                   0,
                   0,
                   InBuffer,
                   v15);
  v12 = AsyncKsecSendResponse(&InBuffer, 0x28u);
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
LABEL_20:
    SendStatusOnlyResponse(a2, v13);
  }
}

```

## disassembly

```asm
0x14000481c  mov     [rsp+arg_10], rbx
0x140004821  push    rdi
0x140004822  sub     rsp, 0A0h
0x140004829  mov     rax, cs:__security_cookie
0x140004830  xor     rax, rsp
0x140004833  mov     [rsp+0A8h+var_10], rax
0x14000483b  mov     rax, cs:gLsapSspiExtension
0x140004842  mov     rbx, rdx
0x140004845  mov     rdi, rcx
0x140004848  test    rax, rax
0x14000484b  jz      loc_140004993
0x140004851  cmp     qword ptr [rax+28h], 0
0x140004856  jz      loc_140004993
0x14000485c  mov     ecx, [rdx+28h]
0x14000485f  cmp     ecx, 78h ; 'x'
0x140004862  jb      loc_14000498C
0x140004868  lea     r8, [rdx+40h]
0x14000486c  mov     rdx, [r8+8]
0x140004870  cmp     rcx, rdx
0x140004873  jb      loc_14000498C
0x140004879  test    rdx, rdx
0x14000487c  jz      short loc_140004889
0x14000487e  lea     rax, [rdx+rbx]
0x140004882  mov     [r8+8], rax
0x140004886  mov     ecx, [rbx+28h]
0x140004889  lea     r10, [rbx+30h]
0x14000488d  mov     eax, ecx
0x14000488f  mov     rdx, [r10+8]
0x140004893  cmp     rax, rdx
0x140004896  jb      loc_14000498C
0x14000489c  test    rdx, rdx
0x14000489f  jz      short loc_1400048A9
0x1400048a1  lea     rax, [rdx+rbx]
0x1400048a5  mov     [r10+8], rax
0x1400048a9  lea     r11, [rbx+60h]
0x1400048ad  mov     rcx, [r11+10h]
0x1400048b1  test    rcx, rcx
0x1400048b4  jz      short loc_1400048CA
0x1400048b6  mov     eax, [rbx+28h]
0x1400048b9  cmp     rax, rcx
0x1400048bc  jb      loc_14000498C
0x1400048c2  lea     rax, [rcx+rbx]
0x1400048c6  mov     [rbx+70h], rax
0x1400048ca  mov     rax, [rbx]
0x1400048cd  lea     rcx, [rbx+54h]
0x1400048d1  cmp     dword ptr [rcx+4], 0
0x1400048d5  xorps   xmm0, xmm0
0x1400048d8  movups  [rsp+0A8h+var_30], xmm0
0x1400048dd  mov     [rsp+0A8h+InBuffer], rax
0x1400048e2  movups  [rsp+0A8h+var_20], xmm0
0x1400048ea  jnz     short loc_1400048F3
0x1400048ec  cmp     dword ptr [rcx], 0
0x1400048ef  jnz     short loc_1400048F3
0x1400048f1  xor     ecx, ecx
0x1400048f3  movzx   eax, word ptr [r8]
0x1400048f7  lea     rdx, [rbx+10h]
0x1400048fb  mov     [rsp+0A8h+var_40], 0
0x140004904  neg     ax
0x140004907  movzx   eax, word ptr [r10]
0x14000490b  mov     [rsp+0A8h+var_48], 0
0x140004914  sbb     r9, r9
0x140004917  and     r9, r8
0x14000491a  neg     ax
0x14000491d  lea     rax, [rsp+0A8h+var_20+8]
0x140004925  mov     [rsp+0A8h+var_50], rax
0x14000492a  sbb     r8, r8
0x14000492d  lea     rax, [rsp+0A8h+var_30+8]
0x140004935  and     r8, r10
0x140004938  mov     [rsp+0A8h+var_58], rax
0x14000493d  mov     eax, [rbx+50h]
0x140004940  mov     [rsp+0A8h+var_60], 0
0x140004948  mov     [rsp+0A8h+var_68], 0
0x140004951  mov     [rsp+0A8h+var_70], 0
0x14000495a  mov     [rsp+0A8h+var_78], r11
0x14000495f  mov     [rsp+0A8h+var_80], rcx
0x140004964  mov     rcx, rdi
0x140004967  mov     [rsp+0A8h+var_88], eax
0x14000496b  call    cs:__imp_SspirAcquireCredentialsHandle
0x140004971  mov     edx, 28h ; '('; nInBufferSize
0x140004976  lea     rcx, [rsp+0A8h+InBuffer]; lpInBuffer
0x14000497b  mov     dword ptr [rsp+0A8h+var_30], eax
0x14000497f  call    AsyncKsecSendResponse
0x140004984  test    eax, eax
0x140004986  jns     short loc_1400049A0
0x140004988  mov     edx, eax
0x14000498a  jmp     short loc_140004998
0x14000498c  mov     edx, 0C0000023h
0x140004991  jmp     short loc_140004998
0x140004993  mov     edx, 0C00000BBh
0x140004998  mov     rcx, rbx
0x14000499b  call    SendStatusOnlyResponse
0x1400049a0  mov     rcx, [rsp+0A8h+var_10]
0x1400049a8  xor     rcx, rsp; StackCookie
0x1400049ab  call    __security_check_cookie
0x1400049b0  mov     rbx, [rsp+0A8h+arg_10]
0x1400049b8  add     rsp, 0A0h
0x1400049bf  pop     rdi
0x1400049c0  retn
```
