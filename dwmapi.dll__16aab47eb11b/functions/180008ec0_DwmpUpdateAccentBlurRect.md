# DwmpUpdateAccentBlurRect

- ea: `0x180008ec0`
- end: `0x180008f9c`
- name: `DwmpUpdateAccentBlurRect`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180003370`
- `0x180008ec0`
- `0x18000af44`
- `0x18000bab0`

## pseudocode

```c
__int64 __fastcall DwmpUpdateAccentBlurRect(__int64 a1, __int128 *a2)
{
  CApiPortClient *v3; // rcx
  __int128 v4; // xmm0
  int v5; // ebx
  unsigned int v7; // edx
  void **v8; // [rsp+40h] [rbp-40h] BYREF
  __int128 v9; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v10; // [rsp+58h] [rbp-28h] BYREF
  _OWORD v11[2]; // [rsp+5Ch] [rbp-24h]
  int v12; // [rsp+98h] [rbp+18h] BYREF

  v12 = 0;
  if ( !a2 )
  {
    v7 = 238;
    v5 = -2147024809;
LABEL_5:
    DoStackCaptureDirect(v5, v7);
    return (unsigned int)v5;
  }
  v3 = (CApiPortClient *)(unsigned int)(*((_DWORD *)a2 + 3) - *((_DWORD *)a2 + 1));
  v10 = 1073741950;
  v8 = &CStandardData::`vftable';
  v11[0] = 0;
  v4 = *a2;
  *(_QWORD *)&v11[0] = a1;
  *(_OWORD *)((char *)v11 + 8) = v4;
  v9 = 0;
  v5 = CApiPortClient::SendRequest(v3, &v10, 28, (const struct CAlpcView **)&v8, &v12, 0, 0);
  std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((_QWORD *)&v9 + 1);
  if ( v5 < 0 )
  {
    v7 = 245;
    goto LABEL_5;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008ec0  mov     [rsp-8+arg_0], rbx
0x180008ec5  push    rbp
0x180008ec6  mov     rbp, rsp
0x180008ec9  sub     rsp, 80h
0x180008ed0  mov     [rbp+arg_8], 0
0x180008ed7  mov     r9, rcx
0x180008eda  test    rdx, rdx
0x180008edd  jz      loc_180008F82
0x180008ee3  mov     r8d, [rdx+8]
0x180008ee7  mov     eax, 0
0x180008eec  sub     r8d, [rdx]
0x180008eef  cmovns  eax, r8d
0x180008ef3  test    eax, eax
0x180008ef5  js      loc_180008F82
0x180008efb  mov     ecx, [rdx+0Ch]
0x180008efe  mov     eax, 0
0x180008f03  sub     ecx, [rdx+4]; this
0x180008f06  cmovns  eax, ecx
0x180008f09  test    eax, eax
0x180008f0b  js      short loc_180008F82
0x180008f0d  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180008f14  mov     [rbp+var_28], 4000007Eh
0x180008f1b  xorps   xmm0, xmm0
0x180008f1e  mov     [rbp+var_40], rax
0x180008f22  xor     eax, eax
0x180008f24  movups  xmmword ptr [rbp+var_24], xmm0
0x180008f28  mov     [rsp+80h+var_50], ax; __int16
0x180008f2d  movups  xmm0, xmmword ptr [rdx]
0x180008f30  mov     [rsp+80h+var_58], rax; void *
0x180008f35  lea     r8d, [rax+1Ch]; __int16
0x180008f39  lea     rax, [rbp+arg_8]
0x180008f3d  mov     qword ptr [rbp+var_24], r9
0x180008f41  movdqu  xmmword ptr [rbp+var_24+8], xmm0
0x180008f46  mov     [rsp+80h+var_60], rax; int *
0x180008f4b  lea     r9, [rbp+var_40]; struct CStandardData *
0x180008f4f  xorps   xmm0, xmm0
0x180008f52  lea     rdx, [rbp+var_28]; void *
0x180008f56  movdqu  [rbp+var_38], xmm0
0x180008f5b  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFAEBVCStandardData@@PEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,CStandardData const &,long *,void *,short)
0x180008f60  lea     rcx, [rbp+var_38+8]
0x180008f64  mov     ebx, eax
0x180008f66  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x180008f6b  test    ebx, ebx
0x180008f6d  js      short loc_180008F95
0x180008f6f  mov     eax, ebx
0x180008f71  mov     rbx, [rsp+80h+arg_0]
0x180008f79  add     rsp, 80h
0x180008f80  pop     rbp
0x180008f81  retn
0x180008f82  mov     edx, 0EEh; unsigned int
0x180008f87  mov     ebx, 80070057h
0x180008f8c  mov     ecx, ebx; int
0x180008f8e  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180008f93  jmp     short loc_180008F6F
0x180008f95  mov     edx, 0F5h
0x180008f9a  jmp     short loc_180008F8C
```
