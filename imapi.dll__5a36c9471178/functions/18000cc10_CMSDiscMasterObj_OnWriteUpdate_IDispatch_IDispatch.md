# CMSDiscMasterObj::OnWriteUpdate(IDispatch *,IDispatch *)

- ea: `0x18000cc10`
- end: `0x18000ce4d`
- name: `?OnWriteUpdate@CMSDiscMasterObj@@UEAAXPEAUIDispatch@@0@Z`
- size: `573`
- prototype: `void __fastcall(CMSDiscMasterObj *__hidden this, struct IDispatch *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000cc10`
- `0x180010a40`
- `0x180010aac`
- `0x180019010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000cc69`
- `KERNEL32!WaitForSingleObject` at `0x18000ccea`
- `KERNEL32!WaitForSingleObject` at `0x18000cc69`
- `KERNEL32!WaitForSingleObject` at `0x18000ccea`

## pseudocode

```c
void __fastcall CMSDiscMasterObj::OnWriteUpdate(CMSDiscMasterObj *this, struct IDispatch *a2, struct IDispatch *a3)
{
  struct IDispatchVtbl *lpVtbl; // rax
  void *v5; // rcx
  void *v6; // rcx
  int v7; // ecx
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // eax
  int v12; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+24h] [rbp-Ch] BYREF
  __int64 v14; // [rsp+28h] [rbp-8h] BYREF
  int v15; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v16; // [rsp+58h] [rbp+28h] BYREF

  lpVtbl = a3->lpVtbl;
  v14 = 0;
  if ( ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a3,
         &GUID_2735413d_7f64_5b0f_8f00_5d77afbe261e,
         &v14) < 0 )
    goto LABEL_13;
  v5 = (void *)*((_QWORD *)this + 53);
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  if ( v5 && !WaitForSingleObject(v5, 0) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 58) + 336LL))(*((_QWORD *)this + 58));
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v14 + 136LL))(v14, &v16);
  if ( v16 < 4 )
    goto LABEL_9;
  switch ( v16 )
  {
    case 4u:
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v14 + 64LL))(v14, &v13);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 80LL))(v14, &v15);
      if ( byte_180022B58 )
      {
        CMyUpdateList::SetDataBurnAddProgress((CMSDiscMasterObj *)((char *)this + 192), v15 - dword_180022B54);
      }
      else
      {
        if ( *((_DWORD *)this + 51) )
        {
          *((_DWORD *)this + 73) |= 0x10u;
          v11 = v13;
          *((_QWORD *)this + 34) = 1;
          *((_DWORD *)this + 81) = 1;
          *((_DWORD *)this + 73) |= 0x100u;
          *((_QWORD *)this + 35) = v11;
          *((_DWORD *)this + 75) = v11;
        }
        byte_180022B58 = 1;
      }
      dword_180022B54 = v15;
      break;
    case 5u:
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 120LL))(v14, &v12);
      if ( *((_DWORD *)this + 51) )
      {
        v7 = ++*((_DWORD *)this + 69);
        v8 = *((_DWORD *)this + 73) | 0x20;
        v9 = *((_DWORD *)this + 68);
        *((_DWORD *)this + 80) = v7;
        *((_DWORD *)this + 81) = v9;
        v10 = *((_DWORD *)this + 70);
        if ( *((_DWORD *)this + 71) != v10 )
        {
          *((_DWORD *)this + 75) = v10;
          v8 |= 0x400u;
        }
        *((_DWORD *)this + 70) = 0;
        if ( v7 != v9 )
          v8 |= 0x40u;
        *((_DWORD *)this + 68) = 0;
        *((_DWORD *)this + 73) = v8 | 0x2000;
        *((_DWORD *)this + 76) = v12;
      }
      break;
    case 6u:
LABEL_9:
      byte_180022B58 = 0;
      break;
  }
  CMyUpdateList::UpdateAll((CMSDiscMasterObj *)((char *)this + 192));
  v6 = (void *)*((_QWORD *)this + 53);
  if ( v6 && !WaitForSingleObject(v6, 0) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 58) + 336LL))(*((_QWORD *)this + 58));
LABEL_13:
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
}

```

## disassembly

```asm
0x18000cc10  mov     [rsp-8+arg_0], rbx
0x18000cc15  mov     [rsp-8+arg_8], rdi
0x18000cc1a  push    rbp
0x18000cc1b  mov     rbp, rsp
0x18000cc1e  sub     rsp, 30h
0x18000cc22  mov     rax, [r8]
0x18000cc25  lea     rdx, _GUID_2735413d_7f64_5b0f_8f00_5d77afbe261e
0x18000cc2c  mov     r9, r8
0x18000cc2f  mov     rbx, rcx
0x18000cc32  xor     edi, edi
0x18000cc34  lea     r8, [rbp+var_8]
0x18000cc38  mov     rcx, r9
0x18000cc3b  mov     [rbp+var_8], rdi
0x18000cc3f  mov     rax, [rax]
0x18000cc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc47  test    eax, eax
0x18000cc49  js      loc_18000CD0A
0x18000cc4f  mov     rcx, [rbx+1A8h]; hHandle
0x18000cc56  mov     [rbp+var_10], edi
0x18000cc59  mov     [rbp+var_C], edi
0x18000cc5c  mov     [rbp+arg_10], edi
0x18000cc5f  mov     [rbp+arg_18], edi
0x18000cc62  test    rcx, rcx
0x18000cc65  jz      short loc_18000CC89
0x18000cc67  xor     edx, edx; dwMilliseconds
0x18000cc69  call    cs:__imp_WaitForSingleObject
0x18000cc6f  test    eax, eax
0x18000cc71  jnz     short loc_18000CC89
0x18000cc73  mov     rcx, [rbx+1D0h]
0x18000cc7a  mov     rax, [rcx]
0x18000cc7d  mov     rax, [rax+150h]
0x18000cc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc89  mov     rcx, [rbp+var_8]
0x18000cc8d  lea     rdx, [rbp+arg_18]
0x18000cc91  mov     rax, [rcx]
0x18000cc94  mov     rax, [rax+88h]
0x18000cc9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca0  mov     ecx, [rbp+arg_18]
0x18000cca3  test    ecx, ecx
0x18000cca5  jz      short loc_18000CCC9
0x18000cca7  sub     ecx, 1
0x18000ccaa  jz      short loc_18000CCC9
0x18000ccac  sub     ecx, 1
0x18000ccaf  jz      short loc_18000CCC9
0x18000ccb1  sub     ecx, 1
0x18000ccb4  jz      short loc_18000CCC9
0x18000ccb6  sub     ecx, 1
0x18000ccb9  jz      loc_18000CDB8
0x18000ccbf  sub     ecx, 1
0x18000ccc2  jz      short loc_18000CD2F
0x18000ccc4  cmp     ecx, 1
0x18000ccc7  jnz     short loc_18000CCD0
0x18000ccc9  mov     cs:byte_180022B58, dil
0x18000ccd0  lea     rcx, [rbx+0C0h]; this
0x18000ccd7  call    ?UpdateAll@CMyUpdateList@@QEAAXXZ; CMyUpdateList::UpdateAll(void)
0x18000ccdc  mov     rcx, [rbx+1A8h]; hHandle
0x18000cce3  test    rcx, rcx
0x18000cce6  jz      short loc_18000CD0A
0x18000cce8  xor     edx, edx; dwMilliseconds
0x18000ccea  call    cs:__imp_WaitForSingleObject
0x18000ccf0  test    eax, eax
0x18000ccf2  jnz     short loc_18000CD0A
0x18000ccf4  mov     rcx, [rbx+1D0h]
0x18000ccfb  mov     rax, [rcx]
0x18000ccfe  mov     rax, [rax+150h]
0x18000cd05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd0a  mov     rcx, [rbp+var_8]
0x18000cd0e  test    rcx, rcx
0x18000cd11  jz      short loc_18000CD1F
0x18000cd13  mov     rax, [rcx]
0x18000cd16  mov     rax, [rax+10h]
0x18000cd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd1f  mov     rbx, [rsp+30h+arg_0]
0x18000cd24  mov     rdi, [rsp+30h+arg_8]
0x18000cd29  add     rsp, 30h
0x18000cd2d  pop     rbp
0x18000cd2e  retn
0x18000cd2f  mov     rcx, [rbp+var_8]
0x18000cd33  lea     rdx, [rbp+var_10]
0x18000cd37  mov     rax, [rcx]
0x18000cd3a  mov     rax, [rax+78h]
0x18000cd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd43  cmp     [rbx+0CCh], edi
0x18000cd49  jz      short loc_18000CCD0
0x18000cd4b  inc     dword ptr [rbx+114h]
0x18000cd51  mov     eax, [rbx+124h]
0x18000cd57  mov     ecx, [rbx+114h]
0x18000cd5d  or      eax, 20h
0x18000cd60  mov     edx, [rbx+110h]
0x18000cd66  mov     [rbx+140h], ecx
0x18000cd6c  mov     [rbx+144h], edx
0x18000cd72  mov     r8d, [rbx+118h]
0x18000cd79  cmp     [rbx+11Ch], r8d
0x18000cd80  jz      short loc_18000CD8D
0x18000cd82  mov     [rbx+12Ch], r8d
0x18000cd89  bts     eax, 0Ah
0x18000cd8d  mov     [rbx+118h], edi
0x18000cd93  cmp     ecx, edx
0x18000cd95  jz      short loc_18000CD9A
0x18000cd97  or      eax, 40h
0x18000cd9a  bts     eax, 0Dh
0x18000cd9e  mov     [rbx+110h], edi
0x18000cda4  mov     [rbx+124h], eax
0x18000cdaa  mov     eax, [rbp+var_10]
0x18000cdad  mov     [rbx+130h], eax
0x18000cdb3  jmp     loc_18000CCD0
0x18000cdb8  mov     rcx, [rbp+var_8]
0x18000cdbc  lea     rdx, [rbp+var_C]
0x18000cdc0  mov     rax, [rcx]
0x18000cdc3  mov     rax, [rax+40h]
0x18000cdc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdcc  mov     rcx, [rbp+var_8]
0x18000cdd0  lea     rdx, [rbp+arg_10]
0x18000cdd4  mov     rax, [rcx]
0x18000cdd7  mov     rax, [rax+50h]
0x18000cddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cde0  cmp     cs:byte_180022B58, dil
0x18000cde7  lea     rcx, [rbx+0C0h]; this
0x18000cdee  jnz     short loc_18000CE31
0x18000cdf0  cmp     [rcx+0Ch], edi
0x18000cdf3  jz      short loc_18000CE28
0x18000cdf5  or      dword ptr [rcx+64h], 10h
0x18000cdf9  mov     eax, [rbp+var_C]
0x18000cdfc  mov     qword ptr [rcx+50h], 1
0x18000ce04  mov     dword ptr [rcx+84h], 1
0x18000ce0e  bts     dword ptr [rbx+124h], 8
0x18000ce16  mov     [rbx+118h], eax
0x18000ce1c  mov     [rbx+11Ch], edi
0x18000ce22  mov     [rbx+12Ch], eax
0x18000ce28  mov     cs:byte_180022B58, 1
0x18000ce2f  jmp     short loc_18000CE3F
0x18000ce31  mov     edx, [rbp+arg_10]
0x18000ce34  sub     edx, cs:dword_180022B54; unsigned int
0x18000ce3a  call    ?SetDataBurnAddProgress@CMyUpdateList@@QEAAEK@Z; CMyUpdateList::SetDataBurnAddProgress(ulong)
0x18000ce3f  mov     eax, [rbp+arg_10]
0x18000ce42  mov     cs:dword_180022B54, eax
0x18000ce48  jmp     loc_18000CCD0
```
