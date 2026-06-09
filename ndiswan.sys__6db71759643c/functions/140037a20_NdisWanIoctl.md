# NdisWanIoctl

- ea: `0x140037a20`
- end: `0x140037b62`
- name: `NdisWanIoctl`
- size: `322`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400359f4`
- `0x140037a20`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140037b0e`
- `ntoskrnl!IofCompleteRequest` at `0x140037b0e`
- `ntoskrnl!IoIs32bitProcess` at `0x140037a5e`
- `ntoskrnl!IoIs32bitProcess` at `0x140037a5e`

## pseudocode

```c
__int64 __fastcall NdisWanIoctl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  _DWORD *p_Type; // r14
  DWORD LowPart; // ebx
  USHORT ShareAccess; // r15
  ULONG Options; // r12d
  unsigned int Length; // ebp
  unsigned __int64 v9; // rbx
  __int64 v10; // rcx
  int v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  __int64 result; // rax
  __int64 v15; // rcx
  CCHAR v16; // dl
  unsigned int v17; // [rsp+68h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  p_Type = &a2->AssociatedIrp.MasterIrp->Type;
  v17 = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  ShareAccess = CurrentStackLocation->Parameters.Create.ShareAccess;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( IoIs32bitProcess(a2) )
    goto LABEL_24;
  if ( CurrentStackLocation->MajorFunction != 14 || ShareAccess != 18 || (LowPart & 3) != 0 )
  {
    a2->IoStatus.Information = 0;
LABEL_24:
    v13 = -1073741637;
    v16 = 0;
    goto LABEL_14;
  }
  v9 = (LowPart >> 2) & 0xFFF;
  if ( (unsigned int)v9 <= 0x2B && (v10 = 0x88000000900LL, _bittest64(&v10, v9))
    || (v11 = (int)p_Type, (_DWORD)v9 == 48) )
  {
    v11 = (int)a2;
  }
  v12 = ExecuteIo(v9, v11, Options, (_DWORD)p_Type, Length, (__int64)&v17);
  v13 = v12;
  if ( v12 == -1073741820 )
  {
    v15 = 4;
    if ( Length < 4 )
    {
      v15 = 0;
    }
    else
    {
      *p_Type = v17;
      v17 = 4;
    }
    v13 = 0;
    goto LABEL_13;
  }
  if ( !v12 )
  {
    v15 = v17;
LABEL_13:
    a2->IoStatus.Information = v15;
    v16 = 2;
LABEL_14:
    a2->IoStatus.Status = v13;
    IofCompleteRequest(a2, v16);
    return v13;
  }
  result = 259;
  if ( v13 != 259 )
  {
    if ( v13 < 0xC0000000 )
      v13 = -1073741823;
    v15 = 0;
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x140037a20  mov     [rsp+arg_0], rbx
0x140037a25  mov     [rsp+arg_10], rbp
0x140037a2a  push    rsi
0x140037a2b  push    rdi
0x140037a2c  push    r12
0x140037a2e  push    r14
0x140037a30  push    r15
0x140037a32  sub     rsp, 30h
0x140037a36  mov     rsi, [rdx+0B8h]
0x140037a3d  mov     rcx, rdx; Irp
0x140037a40  mov     r14, [rdx+18h]
0x140037a44  mov     rdi, rdx
0x140037a47  mov     [rsp+58h+arg_8], 0
0x140037a4f  mov     ebx, [rsi+18h]
0x140037a52  movzx   r15d, word ptr [rsi+1Ah]
0x140037a57  mov     r12d, [rsi+10h]
0x140037a5b  mov     ebp, [rsi+8]
0x140037a5e  call    cs:__imp_IoIs32bitProcess
0x140037a65  nop     dword ptr [rax+rax+00h]
0x140037a6a  test    al, al
0x140037a6c  jnz     loc_140037B59
0x140037a72  cmp     byte ptr [rsi], 0Eh
0x140037a75  jnz     loc_140037B51
0x140037a7b  cmp     r15w, 12h
0x140037a80  jnz     loc_140037B51
0x140037a86  test    bl, 3
0x140037a89  jnz     loc_140037B51
0x140037a8f  shr     ebx, 2
0x140037a92  and     ebx, 0FFFh
0x140037a98  cmp     ebx, 2Bh ; '+'
0x140037a9b  ja      short loc_140037AAD
0x140037a9d  mov     rcx, 88000000900h
0x140037aa7  bt      rcx, rbx
0x140037aab  jb      short loc_140037B1E
0x140037aad  mov     rdx, r14
0x140037ab0  cmp     ebx, 30h ; '0'
0x140037ab3  jz      short loc_140037B1E
0x140037ab5  lea     rax, [rsp+58h+arg_8]
0x140037aba  mov     r9, r14
0x140037abd  mov     [rsp+58h+var_30], rax
0x140037ac2  mov     r8d, r12d
0x140037ac5  mov     ecx, ebx
0x140037ac7  mov     [rsp+58h+var_38], ebp
0x140037acb  call    ExecuteIo
0x140037ad0  mov     ebx, eax
0x140037ad2  cmp     eax, 0C0000004h
0x140037ad7  jz      short loc_140037B35
0x140037ad9  test    eax, eax
0x140037adb  jz      short loc_140037AFE
0x140037add  mov     eax, 103h
0x140037ae2  cmp     ebx, eax
0x140037ae4  jnz     short loc_140037B23
0x140037ae6  mov     rbx, [rsp+58h+arg_0]
0x140037aeb  mov     rbp, [rsp+58h+arg_10]
0x140037af0  add     rsp, 30h
0x140037af4  pop     r15
0x140037af6  pop     r14
0x140037af8  pop     r12
0x140037afa  pop     rdi
0x140037afb  pop     rsi
0x140037afc  retn
0x140037afe  mov     ecx, [rsp+58h+arg_8]
0x140037b02  mov     [rdi+38h], rcx
0x140037b06  mov     dl, 2; PriorityBoost
0x140037b08  mov     rcx, rdi; Irp
0x140037b0b  mov     [rdi+30h], ebx
0x140037b0e  call    cs:__imp_IofCompleteRequest
0x140037b15  nop     dword ptr [rax+rax+00h]
0x140037b1a  mov     eax, ebx
0x140037b1c  jmp     short loc_140037AE6
0x140037b1e  mov     rdx, rdi
0x140037b21  jmp     short loc_140037AB5
0x140037b23  cmp     ebx, 0C0000000h
0x140037b29  mov     eax, 0C0000001h
0x140037b2e  cmovb   ebx, eax
0x140037b31  xor     ecx, ecx
0x140037b33  jmp     short loc_140037B02
0x140037b35  mov     ecx, 4
0x140037b3a  cmp     ebp, ecx
0x140037b3c  jb      short loc_140037B4B
0x140037b3e  mov     eax, [rsp+58h+arg_8]
0x140037b42  mov     [r14], eax
0x140037b45  mov     [rsp+58h+arg_8], ecx
0x140037b49  jmp     short loc_140037B4D
0x140037b4b  xor     ecx, ecx
0x140037b4d  xor     ebx, ebx
0x140037b4f  jmp     short loc_140037B02
0x140037b51  mov     qword ptr [rdi+38h], 0
0x140037b59  mov     ebx, 0C00000BBh
0x140037b5e  xor     edx, edx
0x140037b60  jmp     short loc_140037B08
```
