# ClasspDeviceManageBypassIO

- ea: `0x14002f308`
- end: `0x14002f682`
- name: `ClasspDeviceManageBypassIO`
- size: `890`
- prototype: `NTSTATUS __fastcall(struct _DEVICE_OBJECT *, IRP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x14002f308`
- `0x14003e640`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14002f65d`
- `ntoskrnl!IofCallDriver` at `0x14002f65d`

## string_xrefs

- `0x14002f433`: `Access denied, operation not supported from user mode`

## pseudocode

```c
NTSTATUS __fastcall ClasspDeviceManageBypassIO(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r8
  __int64 v3; // rbp
  __int64 v4; // r13
  unsigned int v7; // esi
  int v8; // edi
  _IRP *MasterIrp; // rbx
  int MdlAddress; // ecx
  int v11; // r12d
  size_t Length; // rdx
  int v13; // ecx
  int v14; // ecx
  $D0800AE58BBC905224E63C4EF774D393 *p_AssociatedIrp; // r15
  const wchar_t *v16; // rax
  _OWORD *v17; // rbx
  _DRIVER_OBJECT *DriverObject; // rcx
  __int64 v19; // rax
  wchar_t *Buffer; // rdx
  size_t v21; // r8
  __int64 v22; // rax
  unsigned __int64 v23; // rcx
  NTSTATUS v24; // ebx
  PDEVICE_OBJECT *DeviceExtension; // rcx
  _IO_STACK_LOCATION *v27; // rax
  __int128 Src; // [rsp+20h] [rbp-58h] BYREF
  wchar_t v29; // [rsp+30h] [rbp-48h]
  const wchar_t *v31; // [rsp+88h] [rbp+10h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = -1;
  v29 = aDriver[8];
  v4 = -1;
  Src = *(_OWORD *)L"\\Driver\\";
  v7 = 0;
  do
    ++v4;
  while ( *((_WORD *)&Src + v4) );
  WORD4(Src) = 0;
  *(_QWORD *)&Src = 0x7300790073002ELL;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x18 )
  {
    v8 = -1073741820;
    goto LABEL_40;
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type != 24 )
  {
    v8 = -1073741637;
    goto LABEL_40;
  }
  MdlAddress = (int)MasterIrp->MdlAddress;
  v11 = 2;
  if ( (unsigned int)(MdlAddress - 1) > 2 )
  {
LABEL_8:
    v8 = -1073741811;
    goto LABEL_40;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( (unsigned int)Length < 8 )
  {
    v8 = -1073741789;
    goto LABEL_40;
  }
  v13 = MdlAddress - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( !v14 )
    {
      p_AssociatedIrp = 0;
      v7 = 24;
      goto LABEL_18;
    }
    if ( v14 != 1 )
      goto LABEL_8;
    v11 = 3;
  }
  else
  {
    v11 = 1;
  }
  v7 = 352;
  p_AssociatedIrp = &MasterIrp->AssociatedIrp;
LABEL_18:
  if ( (unsigned int)Length >= v7 )
  {
    if ( a2->RequestorMode )
    {
      v8 = -1073741790;
      v16 = L"Access denied, operation not supported from user mode";
    }
    else
    {
      if ( v11 == 1 || (unsigned int)(v11 - 2) < 2 )
      {
        DeviceExtension = (PDEVICE_OBJECT *)a1->DeviceExtension;
        *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
        *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                   + 6);
        CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
        CurrentStackLocation[-1].Control = 0;
        v27 = a2->Tail.Overlay.CurrentStackLocation;
        v27[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ClasspDeviceManageBypassIOCompletion;
        v27[-1].Context = 0;
        v27[-1].Control = -32;
        return IofCallDriver(DeviceExtension[2], a2);
      }
      v8 = -1073741811;
      v16 = L"Invalid operation";
    }
    v31 = v16;
    if ( v7 == 24 )
    {
      memset(MasterIrp, 0, Length);
      *(_DWORD *)&MasterIrp->Type = 352;
      *(_DWORD *)(&MasterIrp->Size + 1) = 24;
      LODWORD(MasterIrp->MdlAddress) = v11;
    }
    else
    {
      memset(MasterIrp, 0, Length);
      LODWORD(MasterIrp->MdlAddress) = v11;
      *(_DWORD *)&MasterIrp->Type = 352;
      *(_DWORD *)(&MasterIrp->Size + 1) = 352;
      v17 = (_OWORD *)((char *)&p_AssociatedIrp->SystemBuffer + 6);
      p_AssociatedIrp->IrpCount = v8;
      DriverObject = a1->DriverObject;
      v19 = DriverObject->DriverName.Length;
      Buffer = DriverObject->DriverName.Buffer;
      v21 = v19 - 16;
      if ( (unsigned __int64)(v19 - 8) >= 0x40 )
      {
        if ( v21 >= 0x40 )
        {
          *v17 = *(_OWORD *)&Buffer[(unsigned __int16)v4];
          *(_OWORD *)((char *)&p_AssociatedIrp[2].SystemBuffer + 6) = *(_OWORD *)&Buffer[(unsigned __int16)v4 + 8];
          *(_OWORD *)((char *)&p_AssociatedIrp[4].SystemBuffer + 6) = *(_OWORD *)&Buffer[(unsigned __int16)v4 + 16];
          *(_OWORD *)((char *)&p_AssociatedIrp[6].SystemBuffer + 6) = *(_OWORD *)&Buffer[(unsigned __int16)v4 + 24];
        }
        else
        {
          memmove((char *)&p_AssociatedIrp->SystemBuffer + 6, &Buffer[(unsigned __int16)v4], v21);
          v23 = a1->DriverObject->DriverName.Length;
          memmove((char *)&p_AssociatedIrp->SystemBuffer + 2 * ((v23 >> 1) - (unsigned __int16)v4) + 6, &Src, 80 - v23);
        }
        LOWORD(v22) = 32;
      }
      else
      {
        memmove((char *)&p_AssociatedIrp->SystemBuffer + 6, &Buffer[(unsigned __int16)v4], v21);
        *(void **)((char *)&p_AssociatedIrp->SystemBuffer
                 + 2 * (((unsigned __int64)a1->DriverObject->DriverName.Length >> 1) - (unsigned __int16)v4)
                 + 6) = (void *)0x7300790073002ELL;
        v22 = -1;
        do
          ++v22;
        while ( *((_WORD *)v17 + v22) );
      }
      WORD2(p_AssociatedIrp->SystemBuffer) = v22;
      do
        ++v3;
      while ( v31[v3] );
      if ( (unsigned __int16)v3 >= 0x80u )
        LOWORD(v3) = 128;
      HIWORD(p_AssociatedIrp[8].SystemBuffer) = v3;
      memmove(&p_AssociatedIrp[9], v31, 2LL * (unsigned __int16)v3);
    }
  }
  else
  {
    memset(MasterIrp, 0, CurrentStackLocation->Parameters.Read.Length);
    *(_DWORD *)(&MasterIrp->Size + 1) = v7;
    v8 = 0;
    *(_DWORD *)&MasterIrp->Type = 352;
    v7 = 8;
  }
LABEL_40:
  v24 = 0;
  a2->IoStatus.Information = v7;
  if ( v7 <= 8 )
    v24 = v8;
  a2->IoStatus.Status = v24;
  ClassReleaseRemoveLock(a1, a2);
  ClassCompleteRequest(a1, a2, 0);
  return v24;
}

```

## disassembly

```asm
0x14002f308  mov     [rsp+arg_10], rbx
0x14002f30d  mov     [rsp+DeviceObject], rcx
0x14002f312  push    rbp
0x14002f313  push    rsi
0x14002f314  push    rdi
0x14002f315  push    r12
0x14002f317  push    r13
0x14002f319  push    r14
0x14002f31b  push    r15
0x14002f31d  sub     rsp, 40h
0x14002f321  movzx   eax, word ptr cs:aDriver+10h; ""
0x14002f328  xor     r9d, r9d
0x14002f32b  movups  xmm0, xmmword ptr cs:aDriver; "\\Driver\\"
0x14002f332  mov     r8, [rdx+0B8h]
0x14002f339  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14002f33d  mov     [rsp+78h+var_48], ax
0x14002f342  mov     r13, rbp
0x14002f345  movups  [rsp+78h+Src], xmm0
0x14002f34a  mov     r14, rdx
0x14002f34d  lea     rax, [rsp+78h+Src]
0x14002f352  mov     rdi, rcx
0x14002f355  mov     esi, r9d
0x14002f358  inc     r13
0x14002f35b  cmp     [rax+r13*2], r9w
0x14002f360  jnz     short loc_14002F358
0x14002f362  mov     r11d, 18h
0x14002f368  mov     word ptr [rsp+78h+Src+8], r9w
0x14002f36e  mov     rax, 7300790073002Eh
0x14002f378  mov     qword ptr [rsp+78h+Src], rax
0x14002f37d  cmp     [r8+10h], r11d
0x14002f381  jnb     short loc_14002F38D
0x14002f383  mov     edi, 0C0000004h
0x14002f388  jmp     loc_14002F5D1
0x14002f38d  mov     rbx, [rdx+18h]
0x14002f391  cmp     [rbx], r11d
0x14002f394  jz      short loc_14002F3A0
0x14002f396  mov     edi, 0C00000BBh
0x14002f39b  jmp     loc_14002F5D1
0x14002f3a0  mov     ecx, [rbx+8]
0x14002f3a3  mov     r12d, 2
0x14002f3a9  lea     eax, [rcx-1]
0x14002f3ac  cmp     eax, r12d
0x14002f3af  jbe     short loc_14002F3BB
0x14002f3b1  mov     edi, 0C000000Dh
0x14002f3b6  jmp     loc_14002F5D1
0x14002f3bb  mov     edx, [r8+8]
0x14002f3bf  cmp     edx, 8
0x14002f3c2  jnb     short loc_14002F3CE
0x14002f3c4  mov     edi, 0C0000023h
0x14002f3c9  jmp     loc_14002F5D1
0x14002f3ce  mov     r10d, 160h
0x14002f3d4  sub     ecx, 1
0x14002f3d7  jz      short loc_14002F3F1
0x14002f3d9  sub     ecx, 1
0x14002f3dc  jz      short loc_14002F3E9
0x14002f3de  cmp     ecx, 1
0x14002f3e1  jnz     short loc_14002F3B1
0x14002f3e3  lea     r12d, [rcx+2]
0x14002f3e7  jmp     short loc_14002F3F7
0x14002f3e9  mov     r15, r9
0x14002f3ec  mov     esi, r11d
0x14002f3ef  jmp     short loc_14002F3FE
0x14002f3f1  mov     r12d, 1
0x14002f3f7  mov     esi, r10d
0x14002f3fa  lea     r15, [rbx+18h]
0x14002f3fe  cmp     edx, esi
0x14002f400  jnb     short loc_14002F428
0x14002f402  mov     r8, rdx; Size
0x14002f405  mov     rcx, rbx; void *
0x14002f408  xor     edx, edx; Val
0x14002f40a  call    memset
0x14002f40f  xor     r9d, r9d
0x14002f412  mov     [rbx+4], esi
0x14002f415  mov     edi, r9d
0x14002f418  mov     dword ptr [rbx], 160h
0x14002f41e  mov     esi, 8
0x14002f423  jmp     loc_14002F5D1
0x14002f428  cmp     [r14+40h], r9b
0x14002f42c  jz      short loc_14002F43C
0x14002f42e  mov     edi, 0C0000022h
0x14002f433  lea     rax, aAccessDeniedOp; "Access denied, operation not supported "...
0x14002f43a  jmp     short loc_14002F466
0x14002f43c  mov     eax, r12d
0x14002f43f  sub     eax, 1
0x14002f442  jz      loc_14002F60B
0x14002f448  sub     eax, 1
0x14002f44b  jz      loc_14002F60B
0x14002f451  cmp     eax, 1
0x14002f454  jz      loc_14002F60B
0x14002f45a  mov     edi, 0C000000Dh
0x14002f45f  lea     rax, aInvalidOperati; "Invalid operation"
0x14002f466  mov     [rsp+78h+arg_8], rax
0x14002f46e  cmp     esi, r11d
0x14002f471  jnz     short loc_14002F492
0x14002f473  mov     r8, rdx; Size
0x14002f476  mov     rcx, rbx; void *
0x14002f479  xor     edx, edx; Val
0x14002f47b  call    memset
0x14002f480  mov     dword ptr [rbx], 160h
0x14002f486  mov     [rbx+4], esi
0x14002f489  mov     [rbx+8], r12d
0x14002f48d  jmp     loc_14002F5CE
0x14002f492  cmp     esi, r10d
0x14002f495  jnz     loc_14002F5D1
0x14002f49b  mov     r8, rdx; Size
0x14002f49e  mov     rcx, rbx; void *
0x14002f4a1  xor     edx, edx; Val
0x14002f4a3  call    memset
0x14002f4a8  mov     rax, [rsp+78h+DeviceObject]
0x14002f4b0  mov     [rbx+8], r12d
0x14002f4b4  mov     dword ptr [rbx], 160h
0x14002f4ba  mov     [rbx+4], esi
0x14002f4bd  lea     rbx, [r15+6]
0x14002f4c1  mov     [r15], edi
0x14002f4c4  mov     rcx, [rax+8]
0x14002f4c8  movzx   r12d, r13w
0x14002f4cc  movzx   eax, word ptr [rcx+38h]
0x14002f4d0  mov     rdx, [rcx+40h]
0x14002f4d4  lea     r8, [rax-10h]; Size
0x14002f4d8  add     rax, 0FFFFFFFFFFFFFFF8h
0x14002f4dc  cmp     rax, 40h ; '@'
0x14002f4e0  jnb     short loc_14002F523
0x14002f4e2  lea     rdx, [rdx+r12*2]; Src
0x14002f4e6  mov     rcx, rbx; void *
0x14002f4e9  call    memmove
0x14002f4ee  mov     rcx, [rsp+78h+DeviceObject]
0x14002f4f6  mov     rax, [rcx+8]
0x14002f4fa  movzx   ecx, word ptr [rax+38h]
0x14002f4fe  mov     rax, 7300790073002Eh
0x14002f508  shr     rcx, 1
0x14002f50b  sub     rcx, r12
0x14002f50e  mov     [r15+rcx*2+6], rax
0x14002f513  mov     rax, rbp
0x14002f516  xor     ecx, ecx
0x14002f518  inc     rax
0x14002f51b  cmp     [rbx+rax*2], cx
0x14002f51f  jnz     short loc_14002F518
0x14002f521  jmp     short loc_14002F593
0x14002f523  cmp     r8, 40h ; '@'
0x14002f527  jnb     short loc_14002F568
0x14002f529  lea     rdx, [rdx+r12*2]; Src
0x14002f52d  mov     rcx, rbx; void *
0x14002f530  call    memmove
0x14002f535  mov     rcx, [rsp+78h+DeviceObject]
0x14002f53d  lea     rdx, [rsp+78h+Src]; Src
0x14002f542  mov     r8d, 50h ; 'P'
0x14002f548  mov     rax, [rcx+8]
0x14002f54c  movzx   ecx, word ptr [rax+38h]
0x14002f550  sub     r8, rcx; Size
0x14002f553  shr     rcx, 1
0x14002f556  sub     rcx, r12
0x14002f559  add     rcx, 3
0x14002f55d  lea     rcx, [r15+rcx*2]; void *
0x14002f561  call    memmove
0x14002f566  jmp     short loc_14002F58E
0x14002f568  movups  xmm0, xmmword ptr [rdx+r12*2]
0x14002f56d  movups  xmmword ptr [rbx], xmm0
0x14002f570  movups  xmm1, xmmword ptr [rdx+r12*2+10h]
0x14002f576  movups  xmmword ptr [rbx+10h], xmm1
0x14002f57a  movups  xmm0, xmmword ptr [rdx+r12*2+20h]
0x14002f580  movups  xmmword ptr [rbx+20h], xmm0
0x14002f584  movups  xmm1, xmmword ptr [rdx+r12*2+30h]
0x14002f58a  movups  xmmword ptr [rbx+30h], xmm1
0x14002f58e  xor     ecx, ecx
0x14002f590  lea     eax, [rcx+20h]
0x14002f593  mov     [r15+4], ax
0x14002f598  mov     rax, [rsp+78h+arg_8]
0x14002f5a0  inc     rbp
0x14002f5a3  cmp     [rax+rbp*2], cx
0x14002f5a7  jnz     short loc_14002F5A0
0x14002f5a9  mov     ecx, 80h
0x14002f5ae  cmp     bp, cx
0x14002f5b1  jb      short loc_14002F5B6
0x14002f5b3  movzx   ebp, cx
0x14002f5b6  movzx   r8d, bp
0x14002f5ba  lea     rcx, [r15+48h]; void *
0x14002f5be  add     r8, r8; Size
0x14002f5c1  mov     [r15+46h], bp
0x14002f5c6  mov     rdx, rax; Src
0x14002f5c9  call    memmove
0x14002f5ce  xor     r9d, r9d
0x14002f5d1  mov     ebx, r9d
0x14002f5d4  mov     ecx, esi
0x14002f5d6  mov     [r14+38h], rcx
0x14002f5da  cmp     esi, 8
0x14002f5dd  mov     rcx, [rsp+78h+DeviceObject]; DeviceObject
0x14002f5e5  mov     rdx, r14; Tag
0x14002f5e8  cmovbe  ebx, edi
0x14002f5eb  mov     [r14+30h], ebx
0x14002f5ef  call    ClassReleaseRemoveLock
0x14002f5f4  mov     rcx, [rsp+78h+DeviceObject]; DeviceObject
0x14002f5fc  xor     r8d, r8d; PriorityBoost
0x14002f5ff  mov     rdx, r14; Irp
0x14002f602  call    ClassCompleteRequest
0x14002f607  mov     eax, ebx
0x14002f609  jmp     short loc_14002F669
0x14002f60b  movups  xmm0, xmmword ptr [r8]
0x14002f60f  mov     rcx, [rdi+40h]
0x14002f613  lea     rdx, ClasspDeviceManageBypassIOCompletion
0x14002f61a  movups  xmmword ptr [r8-48h], xmm0
0x14002f61f  movups  xmm1, xmmword ptr [r8+10h]
0x14002f624  movups  xmmword ptr [r8-38h], xmm1
0x14002f629  movups  xmm0, xmmword ptr [r8+20h]
0x14002f62e  movups  xmmword ptr [r8-28h], xmm0
0x14002f633  movsd   xmm1, qword ptr [r8+30h]
0x14002f639  movsd   qword ptr [r8-18h], xmm1
0x14002f63f  mov     [r8-45h], r9b
0x14002f643  mov     rax, [r14+0B8h]
0x14002f64a  mov     [rax-10h], rdx
0x14002f64e  mov     rdx, r14; Irp
0x14002f651  mov     [rax-8], r9
0x14002f655  mov     byte ptr [rax-45h], 0E0h
0x14002f659  mov     rcx, [rcx+10h]; DeviceObject
0x14002f65d  call    cs:__imp_IofCallDriver
0x14002f664  nop     dword ptr [rax+rax+00h]
0x14002f669  mov     rbx, [rsp+78h+arg_10]
0x14002f671  add     rsp, 40h
0x14002f675  pop     r15
0x14002f677  pop     r14
0x14002f679  pop     r13
0x14002f67b  pop     r12
0x14002f67d  pop     rdi
0x14002f67e  pop     rsi
0x14002f67f  pop     rbp
0x14002f680  retn
```
