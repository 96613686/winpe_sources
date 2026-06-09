# NpFsdRead

- ea: `0x14000db40`
- end: `0x14000ddd5`
- name: `NpFsdRead`
- size: `661`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000db40`
- `0x14000dde0`
- `0x14000deb8`
- `0x14000e1b0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000db6c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000db6c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000dbdf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000dbdf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000dcb4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000dcb4`
- `ntoskrnl!IofCompleteRequest` at `0x14000dcf5`
- `ntoskrnl!IofCompleteRequest` at `0x14000dd33`
- `ntoskrnl!IofCompleteRequest` at `0x14000dcf5`
- `ntoskrnl!IofCompleteRequest` at `0x14000dd33`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000dd0b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000dd0b`

## pseudocode

```c
__int64 __fastcall NpFsdRead(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v4; // r8
  __int64 v5; // r9
  PFILE_OBJECT FileObject; // rsi
  __int64 v7; // r15
  ULONG Length; // r13d
  unsigned __int64 v9; // rbx
  __int64 v10; // rbp
  char v11; // dl
  unsigned int v12; // esi
  char v13; // cl
  __int64 v14; // r12
  __int64 v15; // r12
  __int64 *v16; // rbx
  IRP *v17; // rcx
  __int64 DataQueue; // rax
  size_t Size; // [rsp+28h] [rbp-70h]
  __int64 v21[2]; // [rsp+50h] [rbp-48h] BYREF
  int v22[4]; // [rsp+60h] [rbp-38h] BYREF
  __int64 UserBuffer; // [rsp+A8h] [rbp+10h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v21[1] = (__int64)v21;
  v21[0] = (__int64)v21;
  KeEnterCriticalRegion();
  FileObject = CurrentStackLocation->FileObject;
  v7 = 0;
  if ( *(_WORD *)FileObject->FsContext == 514 )
  {
    UserBuffer = (__int64)a2->UserBuffer;
    Length = CurrentStackLocation->Parameters.Read.Length;
    if ( ((__int64)FileObject->FsContext2 & 1) != 0 )
    {
      v9 = (unsigned __int64)FileObject->FsContext2 & 0xFFFFFFFFFFFFFFFCuLL;
      v10 = ((unsigned __int64)FileObject->FsContext2 >> 1) & 1;
      ExAcquirePushLockExclusiveEx(v9 + 64, 0, v4, v5);
      if ( ((__int64)FileObject->FsContext2 & 1) == 0 || (v11 = *(_BYTE *)(v9 + 8), v11 == 1) )
      {
        v12 = -1073741648;
        goto LABEL_18;
      }
      if ( v11 == 2 )
      {
        v12 = -1073741645;
        goto LABEL_18;
      }
      if ( (_DWORD)v10 )
      {
        if ( (unsigned __int16)*(_DWORD *)(*(_QWORD *)(v9 + 40) + 256LL) == 1 )
        {
LABEL_8:
          v12 = -1073741811;
LABEL_18:
          ExReleasePushLockExclusiveEx(v9 + 64, 0);
          goto LABEL_19;
        }
      }
      else if ( !(unsigned __int16)*(_DWORD *)(*(_QWORD *)(v9 + 40) + 256LL) )
      {
        goto LABEL_8;
      }
      v13 = *(_BYTE *)((unsigned int)v10 + v9 + 9);
      v14 = 72;
      if ( !(_DWORD)v10 )
        v14 = 168;
      v15 = v9 + v14;
      if ( *(_DWORD *)(v15 + 16) == 1 )
      {
        LODWORD(Size) = Length;
        DataQueue = NpReadDataQueue(
                      (__int64)v22,
                      v15,
                      0,
                      0,
                      UserBuffer,
                      Size,
                      a2->RequestorMode,
                      v13 & 1,
                      v9,
                      (__int64)v21);
        v7 = *(_QWORD *)(DataQueue + 8);
        v12 = *(_DWORD *)DataQueue;
      }
      else if ( v11 == 4 )
      {
        v12 = -1073741493;
      }
      else if ( (v13 & 2) != 0 )
      {
        v12 = -1073741607;
      }
      else
      {
        LODWORD(Size) = Length;
        v12 = NpAddDataQueueEntry((unsigned int)v10, v9, v15, 0, 0, Size, (__int64)a2, 0, 0);
      }
      if ( v15 )
        NpEventsReadCompleted(v9, v10, v15, v12, v7);
      goto LABEL_18;
    }
    v12 = -1073741648;
  }
  else
  {
    v12 = -1073741811;
  }
LABEL_19:
  v16 = (__int64 *)v21[0];
  while ( v16 != v21 )
  {
    v17 = (IRP *)(v16 - 21);
    v16 = (__int64 *)*v16;
    IofCompleteRequest(v17, 2);
  }
  KeLeaveCriticalRegion();
  if ( v12 != 259 )
  {
    a2->IoStatus.Information = v7;
    a2->IoStatus.Status = v12;
    IofCompleteRequest(a2, 2);
  }
  return v12;
}

```

## disassembly

```asm
0x14000db40  mov     r11, rsp
0x14000db43  push    rsi
0x14000db44  push    rdi
0x14000db45  push    r15
0x14000db47  sub     rsp, 80h
0x14000db4e  lea     rax, [r11-48h]
0x14000db52  mov     [r11+8], rbx
0x14000db56  mov     rbx, [rdx+0B8h]
0x14000db5d  mov     rdi, rdx
0x14000db60  mov     [r11-40h], rax
0x14000db64  lea     rax, [r11-48h]
0x14000db68  mov     [r11-48h], rax
0x14000db6c  call    cs:__imp_KeEnterCriticalRegion
0x14000db73  nop     dword ptr [rax+rax+00h]
0x14000db78  mov     rsi, [rbx+30h]
0x14000db7c  xor     r15d, r15d
0x14000db7f  mov     ecx, 202h
0x14000db84  mov     rax, [rsi+18h]
0x14000db88  cmp     cx, [rax]
0x14000db8b  jnz     loc_14000DDAD
0x14000db91  mov     rax, [rdi+70h]
0x14000db95  mov     [rsp+98h+arg_8], rax
0x14000db9d  mov     rax, [rsi+20h]
0x14000dba1  mov     [rsp+98h+var_20], r13
0x14000dba6  mov     r13d, [rbx+8]
0x14000dbaa  test    al, 1
0x14000dbac  jz      loc_14000DD4E
0x14000dbb2  mov     [rsp+98h+arg_10], rbp
0x14000dbba  xor     edx, edx
0x14000dbbc  mov     rbp, [rsi+20h]
0x14000dbc0  mov     rbx, [rsi+20h]
0x14000dbc4  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000dbc8  shr     rbp, 1
0x14000dbcb  mov     [rsp+98h+arg_18], r12
0x14000dbd3  and     ebp, 1
0x14000dbd6  mov     [rsp+98h+var_28], r14
0x14000dbdb  lea     rcx, [rbx+40h]
0x14000dbdf  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000dbe6  nop     dword ptr [rax+rax+00h]
0x14000dbeb  mov     rax, [rsi+20h]
0x14000dbef  test    al, 1
0x14000dbf1  jz      loc_14000DDA3
0x14000dbf7  movzx   edx, byte ptr [rbx+8]
0x14000dbfb  cmp     dl, 1
0x14000dbfe  jz      loc_14000DDA3
0x14000dc04  cmp     dl, 2
0x14000dc07  jz      loc_14000DDCB
0x14000dc0d  mov     rax, [rbx+28h]
0x14000dc11  mov     ecx, [rax+100h]
0x14000dc17  movzx   ecx, cx
0x14000dc1a  test    ebp, ebp
0x14000dc1c  jz      short loc_14000DC2D
0x14000dc1e  cmp     ecx, 1
0x14000dc21  jnz     short loc_14000DC31
0x14000dc23  mov     esi, 0C000000Dh
0x14000dc28  jmp     loc_14000DCAE
0x14000dc2d  test    ecx, ecx
0x14000dc2f  jz      short loc_14000DC23
0x14000dc31  movzx   ecx, byte ptr [rbp+rbx+9]
0x14000dc36  test    ebp, ebp
0x14000dc38  mov     r12d, 48h ; 'H'
0x14000dc3e  mov     r8d, 0A8h
0x14000dc44  cmovz   r12d, r8d
0x14000dc48  add     r12, rbx
0x14000dc4b  cmp     dword ptr [r12+10h], 1
0x14000dc51  jz      loc_14000DD55
0x14000dc57  cmp     dl, 4
0x14000dc5a  jz      loc_14000DDB7
0x14000dc60  test    cl, 2
0x14000dc63  jnz     loc_14000DDC1
0x14000dc69  mov     dword ptr [rsp+98h+var_58], r15d; int
0x14000dc6e  xor     r9d, r9d; int
0x14000dc71  mov     [rsp+98h+Src], r15; Src
0x14000dc76  mov     r8, r12; int
0x14000dc79  mov     qword ptr [rsp+98h+var_68], rdi; __int64
0x14000dc7e  mov     rdx, rbx; int
0x14000dc81  mov     dword ptr [rsp+98h+Size], r13d; Size
0x14000dc86  mov     ecx, ebp; int
0x14000dc88  mov     dword ptr [rsp+98h+var_78], r15d; int
0x14000dc8d  call    NpAddDataQueueEntry
0x14000dc92  mov     esi, eax
0x14000dc94  test    r12, r12
0x14000dc97  jz      short loc_14000DCAE
0x14000dc99  mov     r9d, esi
0x14000dc9c  mov     [rsp+98h+var_78], r15
0x14000dca1  mov     r8, r12
0x14000dca4  mov     edx, ebp
0x14000dca6  mov     rcx, rbx
0x14000dca9  call    NpEventsReadCompleted
0x14000dcae  xor     edx, edx
0x14000dcb0  lea     rcx, [rbx+40h]
0x14000dcb4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000dcbb  nop     dword ptr [rax+rax+00h]
0x14000dcc0  mov     r14, [rsp+98h+var_28]
0x14000dcc5  mov     r12, [rsp+98h+arg_18]
0x14000dccd  mov     rbp, [rsp+98h+arg_10]
0x14000dcd5  mov     r13, [rsp+98h+var_20]
0x14000dcda  mov     rbx, [rsp+98h+var_48]
0x14000dcdf  lea     rax, [rsp+98h+var_48]
0x14000dce4  cmp     rbx, rax
0x14000dce7  jz      short loc_14000DD0B
0x14000dce9  lea     rcx, [rbx-0A8h]; Irp
0x14000dcf0  mov     dl, 2; PriorityBoost
0x14000dcf2  mov     rbx, [rbx]
0x14000dcf5  call    cs:__imp_IofCompleteRequest
0x14000dcfc  nop     dword ptr [rax+rax+00h]
0x14000dd01  lea     rax, [rsp+98h+var_48]
0x14000dd06  cmp     rbx, rax
0x14000dd09  jnz     short loc_14000DCE9
0x14000dd0b  call    cs:__imp_KeLeaveCriticalRegion
0x14000dd12  nop     dword ptr [rax+rax+00h]
0x14000dd17  mov     rbx, [rsp+98h+arg_0]
0x14000dd1f  cmp     esi, 103h
0x14000dd25  jz      short loc_14000DD3F
0x14000dd27  mov     dl, 2; PriorityBoost
0x14000dd29  mov     [rdi+38h], r15
0x14000dd2d  mov     rcx, rdi; Irp
0x14000dd30  mov     [rdi+30h], esi
0x14000dd33  call    cs:__imp_IofCompleteRequest
0x14000dd3a  nop     dword ptr [rax+rax+00h]
0x14000dd3f  mov     eax, esi
0x14000dd41  add     rsp, 80h
0x14000dd48  pop     r15
0x14000dd4a  pop     rdi
0x14000dd4b  pop     rsi
0x14000dd4c  retn
0x14000dd4e  mov     esi, 0C00000B0h
0x14000dd53  jmp     short loc_14000DCD5
0x14000dd55  lea     rax, [rsp+98h+var_48]
0x14000dd5a  and     ecx, 1
0x14000dd5d  mov     [rsp+98h+var_50], rax; __int64
0x14000dd62  xor     r9d, r9d; int
0x14000dd65  movzx   eax, byte ptr [rdi+40h]
0x14000dd69  xor     r8d, r8d; int
0x14000dd6c  mov     [rsp+98h+var_58], rbx; __int64
0x14000dd71  mov     rdx, r12; int
0x14000dd74  mov     dword ptr [rsp+98h+Src], ecx; int
0x14000dd78  lea     rcx, [rsp+98h+var_38]; int
0x14000dd7d  mov     [rsp+98h+var_68], al; char
0x14000dd81  mov     rax, [rsp+98h+arg_8]
0x14000dd89  mov     dword ptr [rsp+98h+Size], r13d; Size
0x14000dd8e  mov     [rsp+98h+var_78], rax; __int64
0x14000dd93  call    NpReadDataQueue
0x14000dd98  mov     r15, [rax+8]
0x14000dd9c  mov     esi, [rax]
0x14000dd9e  jmp     loc_14000DC94
0x14000dda3  mov     esi, 0C00000B0h
0x14000dda8  jmp     loc_14000DCAE
0x14000ddad  mov     esi, 0C000000Dh
0x14000ddb2  jmp     loc_14000DCDA
0x14000ddb7  mov     esi, 0C000014Bh
0x14000ddbc  jmp     loc_14000DC94
0x14000ddc1  mov     esi, 0C00000D9h
0x14000ddc6  jmp     loc_14000DC94
0x14000ddcb  mov     esi, 0C00000B3h
0x14000ddd0  jmp     loc_14000DCAE
```
