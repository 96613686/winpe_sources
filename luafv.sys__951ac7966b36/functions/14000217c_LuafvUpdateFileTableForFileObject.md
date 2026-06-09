# LuafvUpdateFileTableForFileObject

- ea: `0x14000217c`
- end: `0x14000225a`
- name: `LuafvUpdateFileTableForFileObject`
- size: `222`
- prototype: `void __fastcall(_BYTE *, struct _FLT_INSTANCE *, struct _FILE_OBJECT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140018f70`
- `0x140020450`

## callees

- `0x14000217c`
- `0x140017e60`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x1400021d9`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400021d9`
- `FLTMGR!FltReleaseContext` at `0x140002242`
- `FLTMGR!FltReleaseContext` at `0x140002242`

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
0x14000217c  mov     [rsp+arg_8], rbx
0x140002181  push    rdi
0x140002182  sub     rsp, 20h
0x140002186  mov     [rsp+28h+Context], 0
0x14000218f  mov     rax, r8
0x140002192  mov     r9, rdx
0x140002195  mov     rdi, rcx
0x140002198  test    rcx, rcx
0x14000219b  jnz     short loc_140002208
0x14000219d  test    rax, rax
0x1400021a0  jz      short loc_1400021F2
0x1400021a2  mov     rbx, [r8+18h]
0x1400021a6  test    rbx, rbx
0x1400021a9  jz      short loc_1400021C9
0x1400021ab  mov     ecx, 7666h
0x1400021b0  cmp     [rbx], cx
0x1400021b3  jnz     short loc_1400021C9
0x1400021b5  mov     rcx, [rbx+100h]
0x1400021bc  mov     [rsp+28h+Context], rcx
0x1400021c1  mov     al, [rbx+0FCh]
0x1400021c7  jmp     short loc_140002202
0x1400021c9  test    r9, r9
0x1400021cc  jz      short loc_1400021F2
0x1400021ce  lea     r8, [rsp+28h+Context]; Context
0x1400021d3  mov     rdx, rax; FileObject
0x1400021d6  mov     rcx, r9; Instance
0x1400021d9  call    cs:__imp_FltGetStreamHandleContext
0x1400021e0  nop     dword ptr [rax+rax+00h]
0x1400021e5  test    eax, eax
0x1400021e7  js      short loc_1400021F2
0x1400021e9  mov     rcx, [rsp+28h+Context]
0x1400021ee  xor     ebx, ebx
0x1400021f0  jmp     short loc_1400021FB
0x1400021f2  xor     ebx, ebx
0x1400021f4  xor     ecx, ecx
0x1400021f6  mov     [rsp+28h+Context], rcx
0x1400021fb  test    rcx, rcx
0x1400021fe  jnz     short loc_14000220F
0x140002200  xor     al, al
0x140002202  test    al, al
0x140002204  jnz     short loc_14000220F
0x140002206  jmp     short loc_140002238
0x140002208  xor     ebx, ebx
0x14000220a  mov     [rsp+28h+Context], rcx
0x14000220f  test    byte ptr [rcx+34h], 2
0x140002213  jz      short loc_140002222
0x140002215  mov     rax, [rcx]
0x140002218  mov     rdx, [rax+50h]
0x14000221c  lea     rcx, [rax+30h]
0x140002220  jmp     short loc_140002229
0x140002222  mov     rcx, [rcx]
0x140002225  mov     rdx, [rcx+20h]
0x140002229  call    LuafvUpdateFileTableForFileChange
0x14000222e  test    rdi, rdi
0x140002231  jnz     short loc_14000224E
0x140002233  mov     rcx, [rsp+28h+Context]; Context
0x140002238  test    rbx, rbx
0x14000223b  jnz     short loc_14000224E
0x14000223d  test    rcx, rcx
0x140002240  jz      short loc_14000224E
0x140002242  call    cs:__imp_FltReleaseContext
0x140002249  nop     dword ptr [rax+rax+00h]
0x14000224e  mov     rbx, [rsp+28h+arg_8]
0x140002253  add     rsp, 20h
0x140002257  pop     rdi
0x140002258  retn
```
