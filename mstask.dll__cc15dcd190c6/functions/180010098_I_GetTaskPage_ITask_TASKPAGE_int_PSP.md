# I_GetTaskPage(ITask *,_TASKPAGE,int,_PSP * *)

- ea: `0x180010098`
- end: `0x1800101ad`
- name: `?I_GetTaskPage@@YAJPEAUITask@@W4_TASKPAGE@@HPEAPEAU_PSP@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(struct ITask *, enum _TASKPAGE, int, struct _PSP **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b910`

## callees

- `0x180010098`
- `0x1800105a8`
- `0x180012fe8`
- `0x180016e14`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010192`
- `COMCTL32!__imp_InitCommonControls` at `0x180010134`
- `COMCTL32!__imp_InitCommonControls` at `0x180010134`

## pseudocode

```c
__int64 __fastcall I_GetTaskPage(struct ITask *a1, enum _TASKPAGE a2, int a3, struct _PSP **a4)
{
  struct ITaskVtbl *lpVtbl; // rax
  int v9; // ebx
  unsigned __int16 *v10; // rbx
  int v11; // edi
  int SettingsPage; // eax
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  pv[0] = 0;
  v15 = 0;
  v9 = ((__int64 (__fastcall *)(struct ITask *, GUID *, __int64 *))lpVtbl->QueryInterface)(a1, &IID_IPersistFile, &v15);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v15 + 64LL))(v15, pv);
    if ( v9 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v9 == 1 )
      {
        v9 = -2147286777;
        goto LABEL_15;
      }
      v10 = (unsigned __int16 *)pv[0];
      if ( !pv[0] )
      {
        v9 = -2147024882;
        goto LABEL_15;
      }
      InitCommonControls();
      if ( a2 )
      {
        v11 = a2 - 1;
        if ( v11 )
        {
          if ( v11 != 1 )
          {
            v9 = -2147024809;
            goto LABEL_15;
          }
          SettingsPage = GetSettingsPage(a1, v10, a3, a4);
        }
        else
        {
          SettingsPage = GetSchedulePage(a1, v10, a3, a4);
        }
      }
      else
      {
        SettingsPage = GetGeneralPage(a1, v10, a3, a4);
      }
      v9 = SettingsPage;
    }
  }
LABEL_15:
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180010098  mov     r11, rsp
0x18001009b  mov     [r11+10h], rbx
0x18001009f  mov     [r11+18h], rbp
0x1800100a3  push    rsi
0x1800100a4  push    rdi
0x1800100a5  push    r14
0x1800100a7  sub     rsp, 30h
0x1800100ab  mov     rax, [rcx]
0x1800100ae  mov     r14d, r8d
0x1800100b1  mov     edi, edx
0x1800100b3  mov     qword ptr [r11-28h], 0
0x1800100bb  lea     r8, [r11+8]
0x1800100bf  mov     qword ptr [r11+8], 0
0x1800100c7  lea     rdx, IID_IPersistFile
0x1800100ce  mov     rbp, r9
0x1800100d1  mov     rax, [rax]
0x1800100d4  mov     rsi, rcx
0x1800100d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100dc  mov     ebx, eax
0x1800100de  test    eax, eax
0x1800100e0  js      loc_180010188
0x1800100e6  mov     rcx, [rsp+48h+arg_0]
0x1800100eb  lea     rdx, [rsp+48h+pv]
0x1800100f0  mov     rax, [rcx]
0x1800100f3  mov     rax, [rax+40h]
0x1800100f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100fc  mov     ebx, eax
0x1800100fe  test    eax, eax
0x180010100  js      loc_180010188
0x180010106  mov     rcx, [rsp+48h+arg_0]
0x18001010b  mov     rax, [rcx]
0x18001010e  mov     rax, [rax+10h]
0x180010112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010117  cmp     ebx, 1
0x18001011a  jnz     short loc_180010123
0x18001011c  mov     ebx, 80030107h
0x180010121  jmp     short loc_180010188
0x180010123  mov     rbx, [rsp+48h+pv]
0x180010128  test    rbx, rbx
0x18001012b  jnz     short loc_180010134
0x18001012d  mov     ebx, 8007000Eh
0x180010132  jmp     short loc_180010188
0x180010134  call    cs:__imp_InitCommonControls
0x18001013a  test    edi, edi
0x18001013c  jz      short loc_180010175
0x18001013e  sub     edi, 1
0x180010141  jz      short loc_180010162
0x180010143  cmp     edi, 1
0x180010146  jz      short loc_18001014F
0x180010148  mov     ebx, 80070057h
0x18001014d  jmp     short loc_180010188
0x18001014f  mov     r9, rbp; struct _PSP **
0x180010152  mov     r8d, r14d; int
0x180010155  mov     rdx, rbx; unsigned __int16 *
0x180010158  mov     rcx, rsi; struct ITask *
0x18001015b  call    ?GetSettingsPage@@YAJPEAUITask@@PEAGHPEAPEAU_PSP@@@Z; GetSettingsPage(ITask *,ushort *,int,_PSP * *)
0x180010160  jmp     short loc_180010186
0x180010162  mov     r9, rbp; struct _PSP **
0x180010165  mov     r8d, r14d; int
0x180010168  mov     rdx, rbx; Src
0x18001016b  mov     rcx, rsi; struct ITask *
0x18001016e  call    ?GetSchedulePage@@YAJPEAUITask@@PEAGHPEAPEAU_PSP@@@Z; GetSchedulePage(ITask *,ushort *,int,_PSP * *)
0x180010173  jmp     short loc_180010186
0x180010175  mov     r9, rbp; struct _PSP **
0x180010178  mov     r8d, r14d; int
0x18001017b  mov     rdx, rbx; unsigned __int16 *
0x18001017e  mov     rcx, rsi; struct ITask *
0x180010181  call    ?GetGeneralPage@@YAJPEAUITask@@PEAGHPEAPEAU_PSP@@@Z; GetGeneralPage(ITask *,ushort *,int,_PSP * *)
0x180010186  mov     ebx, eax
0x180010188  mov     rcx, [rsp+48h+pv]; pv
0x18001018d  test    rcx, rcx
0x180010190  jz      short loc_180010198
0x180010192  call    cs:__imp_CoTaskMemFree
0x180010198  mov     rbp, [rsp+48h+arg_10]
0x18001019d  mov     eax, ebx
0x18001019f  mov     rbx, [rsp+48h+arg_8]
0x1800101a4  add     rsp, 30h
0x1800101a8  pop     r14
0x1800101aa  pop     rdi
0x1800101ab  pop     rsi
0x1800101ac  retn
```
