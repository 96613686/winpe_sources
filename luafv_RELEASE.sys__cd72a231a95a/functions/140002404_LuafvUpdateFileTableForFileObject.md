# LuafvUpdateFileTableForFileObject

- ea: `0x140002404`
- end: `0x1400024e2`
- name: `LuafvUpdateFileTableForFileObject`
- size: `222`
- prototype: `void __fastcall(_BYTE *, struct _FLT_INSTANCE *, struct _FILE_OBJECT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140018f20`
- `0x140020400`

## callees

- `0x140002404`
- `0x140017e10`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x140002461`
- `FLTMGR!FltGetStreamHandleContext` at `0x140002461`
- `FLTMGR!FltReleaseContext` at `0x1400024ca`
- `FLTMGR!FltReleaseContext` at `0x1400024ca`

## pseudocode

```c
void __fastcall LuafvUpdateFileTableForFileObject(_BYTE *a1, struct _FLT_INSTANCE *a2, struct _FILE_OBJECT *a3)
{
  _BYTE *v3; // rdi
  _QWORD *FsContext; // rbx
  char v5; // al
  __int64 v6; // rdx
  __int64 v7; // rcx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  Context = 0;
  v3 = a1;
  if ( a1 )
  {
    FsContext = 0;
    Context = a1;
    goto LABEL_15;
  }
  if ( !a3 )
    goto LABEL_9;
  FsContext = a3->FsContext;
  if ( !FsContext || *(_WORD *)FsContext != 30310 )
  {
    if ( a2 && FltGetStreamHandleContext(a2, a3, &Context) >= 0 )
    {
      a1 = Context;
      FsContext = 0;
LABEL_10:
      if ( a1 )
        goto LABEL_15;
      v5 = 0;
      goto LABEL_12;
    }
LABEL_9:
    FsContext = 0;
    a1 = 0;
    Context = 0;
    goto LABEL_10;
  }
  a1 = (_BYTE *)FsContext[32];
  Context = a1;
  v5 = *((_BYTE *)FsContext + 252);
LABEL_12:
  if ( !v5 )
  {
LABEL_20:
    if ( !FsContext )
    {
      if ( a1 )
        FltReleaseContext(a1);
    }
    return;
  }
LABEL_15:
  if ( (a1[52] & 2) != 0 )
  {
    v6 = *(_QWORD *)(*(_QWORD *)a1 + 80LL);
    v7 = *(_QWORD *)a1 + 48LL;
  }
  else
  {
    v7 = *(_QWORD *)a1;
    v6 = *(_QWORD *)(v7 + 32);
  }
  LuafvUpdateFileTableForFileChange(v7, v6);
  if ( !v3 )
  {
    a1 = Context;
    goto LABEL_20;
  }
}

```

## disassembly

```asm
0x140002404  mov     [rsp+arg_8], rbx
0x140002409  push    rdi
0x14000240a  sub     rsp, 20h
0x14000240e  mov     [rsp+28h+Context], 0
0x140002417  mov     rax, r8
0x14000241a  mov     r9, rdx
0x14000241d  mov     rdi, rcx
0x140002420  test    rcx, rcx
0x140002423  jnz     short loc_140002490
0x140002425  test    rax, rax
0x140002428  jz      short loc_14000247A
0x14000242a  mov     rbx, [r8+18h]
0x14000242e  test    rbx, rbx
0x140002431  jz      short loc_140002451
0x140002433  mov     ecx, 7666h
0x140002438  cmp     [rbx], cx
0x14000243b  jnz     short loc_140002451
0x14000243d  mov     rcx, [rbx+100h]
0x140002444  mov     [rsp+28h+Context], rcx
0x140002449  mov     al, [rbx+0FCh]
0x14000244f  jmp     short loc_14000248A
0x140002451  test    r9, r9
0x140002454  jz      short loc_14000247A
0x140002456  lea     r8, [rsp+28h+Context]; Context
0x14000245b  mov     rdx, rax; FileObject
0x14000245e  mov     rcx, r9; Instance
0x140002461  call    cs:__imp_FltGetStreamHandleContext
0x140002468  nop     dword ptr [rax+rax+00h]
0x14000246d  test    eax, eax
0x14000246f  js      short loc_14000247A
0x140002471  mov     rcx, [rsp+28h+Context]
0x140002476  xor     ebx, ebx
0x140002478  jmp     short loc_140002483
0x14000247a  xor     ebx, ebx
0x14000247c  xor     ecx, ecx
0x14000247e  mov     [rsp+28h+Context], rcx
0x140002483  test    rcx, rcx
0x140002486  jnz     short loc_140002497
0x140002488  xor     al, al
0x14000248a  test    al, al
0x14000248c  jnz     short loc_140002497
0x14000248e  jmp     short loc_1400024C0
0x140002490  xor     ebx, ebx
0x140002492  mov     [rsp+28h+Context], rcx
0x140002497  test    byte ptr [rcx+34h], 2
0x14000249b  jz      short loc_1400024AA
0x14000249d  mov     rax, [rcx]
0x1400024a0  mov     rdx, [rax+50h]
0x1400024a4  lea     rcx, [rax+30h]
0x1400024a8  jmp     short loc_1400024B1
0x1400024aa  mov     rcx, [rcx]
0x1400024ad  mov     rdx, [rcx+20h]
0x1400024b1  call    LuafvUpdateFileTableForFileChange
0x1400024b6  test    rdi, rdi
0x1400024b9  jnz     short loc_1400024D6
0x1400024bb  mov     rcx, [rsp+28h+Context]; Context
0x1400024c0  test    rbx, rbx
0x1400024c3  jnz     short loc_1400024D6
0x1400024c5  test    rcx, rcx
0x1400024c8  jz      short loc_1400024D6
0x1400024ca  call    cs:__imp_FltReleaseContext
0x1400024d1  nop     dword ptr [rax+rax+00h]
0x1400024d6  mov     rbx, [rsp+28h+arg_8]
0x1400024db  add     rsp, 20h
0x1400024df  pop     rdi
0x1400024e0  retn
```
