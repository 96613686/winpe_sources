# LuafvPreWrite

- ea: `0x140001440`
- end: `0x140001606`
- name: `LuafvPreWrite`
- size: `454`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140018220`
- `0x140020630`
- `0x140020ba0`
- `0x140020f70`
- `0x140021040`

## callees

- `0x140001440`
- `0x140001adc`
- `0x140015388`
- `0x1400185bc`

## import_xrefs

- `FLTMGR!FltSetCallbackDataDirty` at `0x14000155e`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000155e`
- `FLTMGR!FltGetStreamHandleContext` at `0x14000148f`
- `FLTMGR!FltGetStreamHandleContext` at `0x14000148f`
- `FLTMGR!FltWriteFile` at `0x1400015ed`
- `FLTMGR!FltWriteFile` at `0x1400015ed`

## pseudocode

```c
__int64 __fastcall LuafvPreWrite(PFLT_CALLBACK_DATA Data, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rcx
  unsigned int v7; // ebp
  __int64 v9; // rdi
  int v10; // eax
  _QWORD *v11; // rdx
  NTSTATUS v12; // eax
  struct _FILE_OBJECT *v13; // rdx
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  ULONG Length; // r9d
  PVOID Buffer; // rax
  PFLT_CONTEXT Context; // [rsp+98h] [rbp+10h] BYREF

  v4 = *(_QWORD *)(a2 + 32);
  Context = 0;
  v7 = 1;
  if ( !v4 || (v9 = *(_QWORD *)(v4 + 24)) == 0 || *(_WORD *)v9 != 30310 )
  {
    if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( Data->Iopb->MajorFunction == 4
        && FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
      {
        if ( Context )
        {
          if ( (*((_BYTE *)Context + 53) & 0x30) == 0x10 )
          {
            v13 = (struct _FILE_OBJECT *)*((_QWORD *)Context + 4);
            if ( v13 )
            {
              Iopb = Data->Iopb;
              Length = Iopb->Parameters.Read.Length;
              if ( Length )
              {
                Buffer = Iopb->Parameters.CreatePipe.Parameters;
                if ( Buffer )
                {
                  v10 = FltWriteFile(
                          *(PFLT_INSTANCE *)(a2 + 24),
                          v13,
                          &Iopb->Parameters.Read.ByteOffset,
                          Length,
                          Buffer,
                          0,
                          0,
                          0,
                          0);
                  if ( v10 < 0 )
                    goto LABEL_10;
                }
              }
            }
          }
        }
      }
    }
    return v7;
  }
  Context = *(PFLT_CONTEXT *)(v9 + 256);
  if ( *(_QWORD *)(v9 + 240) )
  {
    if ( Data->Iopb->MajorFunction == 8 && !*(_BYTE *)(v4 + 75) )
    {
      Data->IoStatus.Status = -1073741757;
      goto LABEL_12;
    }
    if ( !*(_BYTE *)(v9 + 252) )
    {
      v12 = LuafvPerformDelayedVirtualization(a2, Data, v9);
      if ( v12 < 0 )
      {
        v11 = Context;
        Data->IoStatus.Status = v12;
        Data->IoStatus.Information = 0;
        LuafvLogFileError(Data, *v11, LuafvPerformDelayedFailed, (unsigned int)v12);
        return 4;
      }
    }
    Data->Iopb->TargetFileObject = *(PFILE_OBJECT *)(v9 + 240);
    FltSetCallbackDataDirty(Data);
    if ( Data->Iopb->MajorFunction == 4 )
    {
      *a3 = v9;
      return 0;
    }
    return v7;
  }
  v10 = *(_DWORD *)(v9 + 248);
LABEL_10:
  Data->IoStatus.Status = v10;
LABEL_12:
  Data->IoStatus.Information = 0;
  return 4;
}

```

## disassembly

```asm
0x140001440  mov     rax, rsp
0x140001443  push    rbx
0x140001444  push    rbp
0x140001445  push    rsi
0x140001446  push    rdi
0x140001447  push    r14
0x140001449  push    r15
0x14000144b  sub     rsp, 58h
0x14000144f  xor     r15d, r15d
0x140001452  mov     rbx, rcx
0x140001455  mov     rcx, [rdx+20h]
0x140001459  mov     r14, r8
0x14000145c  mov     [rax+10h], r15
0x140001460  mov     rsi, rdx
0x140001463  lea     ebp, [r15+1]
0x140001467  test    rcx, rcx
0x14000146a  jnz     short loc_1400014B3
0x14000146c  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140001471  test    eax, eax
0x140001473  jz      short loc_1400014A3
0x140001475  mov     rax, [rbx+10h]
0x140001479  cmp     byte ptr [rax+4], 4
0x14000147d  jnz     short loc_1400014A3
0x14000147f  mov     rdx, [rsi+20h]; FileObject
0x140001483  lea     r8, [rsp+88h+Context]; Context
0x14000148b  mov     rcx, [rsi+18h]; Instance
0x14000148f  call    cs:__imp_FltGetStreamHandleContext
0x140001496  nop     dword ptr [rax+rax+00h]
0x14000149b  test    eax, eax
0x14000149d  jns     loc_140001583
0x1400014a3  mov     eax, ebp
0x1400014a5  add     rsp, 58h
0x1400014a9  pop     r15
0x1400014ab  pop     r14
0x1400014ad  pop     rdi
0x1400014ae  pop     rsi
0x1400014af  pop     rbp
0x1400014b0  pop     rbx
0x1400014b1  retn
0x1400014b3  mov     rdi, [rcx+18h]
0x1400014b7  test    rdi, rdi
0x1400014ba  jz      short loc_14000146C
0x1400014bc  mov     eax, 7666h
0x1400014c1  cmp     [rdi], ax
0x1400014c4  jnz     short loc_14000146C
0x1400014c6  mov     rax, [rdi+100h]
0x1400014cd  mov     [rsp+88h+Context], rax
0x1400014d5  cmp     [rdi+0F0h], r15
0x1400014dc  jnz     short loc_140001521
0x1400014de  mov     eax, [rdi+0F8h]
0x1400014e4  mov     [rbx+18h], eax
0x1400014e7  jmp     short loc_1400014F0
0x1400014e9  mov     dword ptr [rbx+18h], 0C0000043h
0x1400014f0  mov     [rbx+20h], r15
0x1400014f4  jmp     short loc_14000151A
0x1400014f6  mov     rdx, [rsp+88h+Context]
0x1400014fe  lea     r8, LuafvPerformDelayedFailed
0x140001505  mov     [rbx+18h], eax
0x140001508  mov     r9d, eax
0x14000150b  mov     [rbx+20h], r15
0x14000150f  mov     rcx, rbx
0x140001512  mov     rdx, [rdx]
0x140001515  call    LuafvLogFileError
0x14000151a  mov     eax, 4
0x14000151f  jmp     short loc_1400014A5
0x140001521  mov     rax, [rbx+10h]
0x140001525  cmp     byte ptr [rax+4], 8
0x140001529  jnz     short loc_140001531
0x14000152b  cmp     [rcx+4Bh], r15b
0x14000152f  jz      short loc_1400014E9
0x140001531  cmp     [rdi+0FCh], r15b
0x140001538  jnz     short loc_14000154C
0x14000153a  mov     r8, rdi
0x14000153d  mov     rdx, rbx
0x140001540  mov     rcx, rsi
0x140001543  call    LuafvPerformDelayedVirtualization
0x140001548  test    eax, eax
0x14000154a  js      short loc_1400014F6
0x14000154c  mov     rcx, [rbx+10h]
0x140001550  mov     rax, [rdi+0F0h]
0x140001557  mov     [rcx+8], rax
0x14000155b  mov     rcx, rbx; Data
0x14000155e  call    cs:__imp_FltSetCallbackDataDirty
0x140001565  nop     dword ptr [rax+rax+00h]
0x14000156a  mov     rax, [rbx+10h]
0x14000156e  cmp     byte ptr [rax+4], 4
0x140001572  jnz     loc_1400014A3
0x140001578  mov     [r14], rdi
0x14000157b  mov     ebp, r15d
0x14000157e  jmp     loc_1400014A3
0x140001583  mov     rcx, [rsp+88h+Context]
0x14000158b  test    rcx, rcx
0x14000158e  jz      loc_1400014A3
0x140001594  mov     al, [rcx+35h]
0x140001597  and     al, 30h
0x140001599  cmp     al, 10h
0x14000159b  jnz     loc_1400014A3
0x1400015a1  mov     rdx, [rcx+20h]; FileObject
0x1400015a5  test    rdx, rdx
0x1400015a8  jz      loc_1400014A3
0x1400015ae  mov     r8, [rbx+10h]
0x1400015b2  mov     r9d, [r8+18h]; Length
0x1400015b6  test    r9d, r9d
0x1400015b9  jz      loc_1400014A3
0x1400015bf  mov     rax, [r8+30h]
0x1400015c3  test    rax, rax
0x1400015c6  jz      loc_1400014A3
0x1400015cc  mov     rcx, [rsi+18h]; InitiatingInstance
0x1400015d0  add     r8, 28h ; '('; ByteOffset
0x1400015d4  mov     [rsp+88h+CallbackContext], r15; CallbackContext
0x1400015d9  mov     [rsp+88h+CallbackRoutine], r15; CallbackRoutine
0x1400015de  mov     [rsp+88h+BytesWritten], r15; BytesWritten
0x1400015e3  mov     [rsp+88h+Flags], r15d; Flags
0x1400015e8  mov     [rsp+88h+Buffer], rax; Buffer
0x1400015ed  call    cs:__imp_FltWriteFile
0x1400015f4  nop     dword ptr [rax+rax+00h]
0x1400015f9  test    eax, eax
0x1400015fb  js      loc_1400014E4
0x140001601  jmp     loc_1400014A3
```
