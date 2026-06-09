# CFontFolderViewCallback::s_CanActivationButtonBeShown(IShellItemArray *,int *,ulong)

- ea: `0x18002bba4`
- end: `0x18002bcaf`
- name: `?s_CanActivationButtonBeShown@CFontFolderViewCallback@@SAJPEAUIShellItemArray@@PEAHK@Z`
- size: `267`
- prototype: `__int64 __fastcall(struct IShellItemArray *, int *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bcc0`
- `0x18002bce0`

## callees

- `0x180022810`
- `0x18002a4fc`
- `0x18002bba4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc60`

## pseudocode

```c
__int64 __fastcall CFontFolderViewCallback::s_CanActivationButtonBeShown(struct IShellItemArray *a1, int *a2, int a3)
{
  struct IShellItemArrayVtbl *lpVtbl; // rax
  int PidlFromShellItem; // ebx
  int v8; // edi
  unsigned int v9; // ebp
  struct IShellItemArrayVtbl *v10; // rax
  unsigned int ActivationStatus; // eax
  struct IShellItem *v13; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  if ( a1 )
  {
    lpVtbl = a1->lpVtbl;
    v14 = 0;
    PidlFromShellItem = ((__int64 (__fastcall *)(struct IShellItemArray *, unsigned int *))lpVtbl->GetCount)(a1, &v14);
    if ( PidlFromShellItem >= 0 )
    {
      v8 = 0;
      v9 = 0;
      if ( v14 )
      {
        while ( PidlFromShellItem >= 0 )
        {
          v10 = a1->lpVtbl;
          v13 = 0;
          PidlFromShellItem = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))v10->GetItemAt)(
                                a1,
                                v9,
                                &v13);
          if ( PidlFromShellItem >= 0 )
          {
            pv = 0;
            PidlFromShellItem = GetPidlFromShellItem(v13, (struct _ITEMIDLIST **)&pv);
            if ( PidlFromShellItem >= 0 )
            {
              ActivationStatus = FID_GetActivationStatus((const struct _ITEMIDLIST *)pv);
              if ( a3 == ActivationStatus || ActivationStatus == 2 )
                v8 = 1;
              CoTaskMemFree(pv);
            }
            ((void (__fastcall *)(struct IShellItem *))v13->lpVtbl->Release)(v13);
          }
          if ( ++v9 >= v14 )
          {
            if ( PidlFromShellItem < 0 )
              return (unsigned int)PidlFromShellItem;
            goto LABEL_14;
          }
        }
      }
      else
      {
LABEL_14:
        *a2 = v8 == 0 ? 3 : 0;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)PidlFromShellItem;
}

```

## disassembly

```asm
0x18002bba4  mov     [rsp+arg_8], rbx
0x18002bba9  push    rbp
0x18002bbaa  push    rsi
0x18002bbab  push    rdi
0x18002bbac  push    r14
0x18002bbae  push    r15
0x18002bbb0  sub     rsp, 30h
0x18002bbb4  mov     r15d, r8d
0x18002bbb7  mov     r14, rdx
0x18002bbba  mov     rsi, rcx
0x18002bbbd  test    rcx, rcx
0x18002bbc0  jz      loc_18002BC97
0x18002bbc6  mov     rax, [rcx]
0x18002bbc9  lea     rdx, [rsp+58h+arg_0]
0x18002bbce  mov     [rsp+58h+arg_0], 0
0x18002bbd6  mov     rax, [rax+38h]
0x18002bbda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbdf  mov     ebx, eax
0x18002bbe1  test    eax, eax
0x18002bbe3  js      loc_18002BC9C
0x18002bbe9  xor     edi, edi
0x18002bbeb  xor     ebp, ebp
0x18002bbed  cmp     [rsp+58h+arg_0], edi
0x18002bbf1  jbe     loc_18002BC89
0x18002bbf7  test    ebx, ebx
0x18002bbf9  js      loc_18002BC9C
0x18002bbff  mov     rax, [rsi]
0x18002bc02  lea     r8, [rsp+58h+var_38]
0x18002bc07  mov     edx, ebp
0x18002bc09  mov     [rsp+58h+var_38], 0
0x18002bc12  mov     rcx, rsi
0x18002bc15  mov     rax, [rax+40h]
0x18002bc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc1e  mov     ebx, eax
0x18002bc20  test    eax, eax
0x18002bc22  js      short loc_18002BC77
0x18002bc24  mov     rcx, [rsp+58h+var_38]; struct IShellItem *
0x18002bc29  lea     rdx, [rsp+58h+pv]; struct _ITEMIDLIST **
0x18002bc2e  mov     [rsp+58h+pv], 0
0x18002bc37  call    ?GetPidlFromShellItem@@YAJPEAUIShellItem@@PEAPEFAU_ITEMIDLIST@@@Z; GetPidlFromShellItem(IShellItem *,_ITEMIDLIST * *)
0x18002bc3c  mov     ebx, eax
0x18002bc3e  test    eax, eax
0x18002bc40  js      short loc_18002BC66
0x18002bc42  mov     rcx, [rsp+58h+pv]; struct _ITEMIDLIST *
0x18002bc47  call    ?FID_GetActivationStatus@@YAKPEFBU_ITEMIDLIST@@@Z; FID_GetActivationStatus(_ITEMIDLIST const *)
0x18002bc4c  cmp     r15d, eax
0x18002bc4f  jz      short loc_18002BC56
0x18002bc51  cmp     eax, 2
0x18002bc54  jnz     short loc_18002BC5B
0x18002bc56  mov     edi, 1
0x18002bc5b  mov     rcx, [rsp+58h+pv]; pv
0x18002bc60  call    cs:__imp_CoTaskMemFree
0x18002bc66  mov     rcx, [rsp+58h+var_38]
0x18002bc6b  mov     rax, [rcx]
0x18002bc6e  mov     rax, [rax+10h]
0x18002bc72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc77  inc     ebp
0x18002bc79  mov     eax, ebx
0x18002bc7b  cmp     ebp, [rsp+58h+arg_0]
0x18002bc7f  jb      loc_18002BBF7
0x18002bc85  test    eax, eax
0x18002bc87  js      short loc_18002BC9C
0x18002bc89  neg     edi
0x18002bc8b  sbb     eax, eax
0x18002bc8d  not     eax
0x18002bc8f  and     eax, 3
0x18002bc92  mov     [r14], eax
0x18002bc95  jmp     short loc_18002BC9C
0x18002bc97  mov     ebx, 80070057h
0x18002bc9c  mov     eax, ebx
0x18002bc9e  mov     rbx, [rsp+58h+arg_8]
0x18002bca3  add     rsp, 30h
0x18002bca7  pop     r15
0x18002bca9  pop     r14
0x18002bcab  pop     rdi
0x18002bcac  pop     rsi
0x18002bcad  pop     rbp
0x18002bcae  retn
```
