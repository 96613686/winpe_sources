# DrGetConnectionId(_RX_CONTEXT *,_UNICODE_STRING *,_RX_CONNECTION_ID *)

- ea: `0x140028b40`
- end: `0x140028cb2`
- name: `?DrGetConnectionId@@YAJPEAU_RX_CONTEXT@@PEAU_UNICODE_STRING@@PEAU_RX_CONNECTION_ID@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(struct _RX_CONTEXT *, struct _UNICODE_STRING *, struct _RX_CONNECTION_ID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000324c`
- `0x140028b40`

## import_xrefs

- `ntoskrnl!SeQuerySessionIdToken` at `0x140028ca1`
- `ntoskrnl!SeQuerySessionIdToken` at `0x140028ca1`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140028bff`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140028bff`

## pseudocode

```c
__int64 __fastcall DrGetConnectionId(struct _RX_CONTEXT *a1, struct _UNICODE_STRING *a2, struct _RX_CONNECTION_ID *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  ULONG v5; // r9d
  PFILE_OBJECT FileObject; // r11
  unsigned int v7; // ecx
  unsigned __int16 Length; // r10
  wchar_t *Buffer; // rax
  wchar_t *v10; // rdx
  __int16 v11; // cx
  __int16 v12; // ax
  unsigned __int16 v13; // ax
  PACCESS_STATE AccessState; // rcx
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  SECURITY_SUBJECT_CONTEXT *p_SubjectSecurityContext; // rcx
  PACCESS_TOKEN ClientToken; // rcx
  UNICODE_STRING String; // [rsp+20h] [rbp-18h] BYREF
  ULONG SessionId; // [rsp+40h] [rbp+8h] BYREF
  ULONG Value; // [rsp+50h] [rbp+18h] BYREF

  CurrentStackLocation = a1->CurrentIrp->Tail.Overlay.CurrentStackLocation;
  SessionId = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  v5 = -1;
  *(_OWORD *)&a3->SessionID = 0;
  FileObject = CurrentStackLocation->FileObject;
  v7 = 0;
  Value = -1;
  String = 0;
  Length = FileObject->FileName.Length;
  Buffer = FileObject->FileName.Buffer;
  while ( v7 < FileObject->FileName.Length >> 1 )
  {
    v10 = Buffer + 1;
    if ( *Buffer == 58 )
    {
      v11 = 2 * v7;
      v12 = FileObject->FileName.MaximumLength - v11;
      String.Buffer = v10;
      String.MaximumLength = v12 - 2;
      v13 = *v10 - 48;
      String.Length = Length - v11 - 2;
      if ( v13 <= 9u )
      {
        if ( RtlUnicodeStringToInteger(&String, 0, &Value) )
          v5 = -1;
        else
          v5 = Value;
      }
      break;
    }
    ++Buffer;
    ++v7;
  }
  SessionId = v5;
  if ( v5 == -1 )
  {
    if ( CurrentStackLocation->MajorFunction == 14 )
    {
      if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1311119 )
        goto LABEL_12;
      AccessState = *(PACCESS_STATE *)(*(_QWORD *)&CurrentStackLocation->Parameters.CreatePipe.Parameters->CompletionMode
                                     + 8LL);
    }
    else
    {
      if ( CurrentStackLocation->MajorFunction )
        goto LABEL_12;
      SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
      if ( !SecurityContext )
        goto LABEL_12;
      AccessState = SecurityContext->AccessState;
    }
    p_SubjectSecurityContext = &AccessState->SubjectSecurityContext;
    if ( p_SubjectSecurityContext )
    {
      if ( p_SubjectSecurityContext->ClientToken )
        ClientToken = p_SubjectSecurityContext->ClientToken;
      else
        ClientToken = p_SubjectSecurityContext->PrimaryToken;
      SeQuerySessionIdToken(ClientToken, &SessionId);
    }
  }
LABEL_12:
  a3[1].SessionID = SessionId;
  return 0;
}

```

## disassembly

```asm
0x140028b40  mov     [rsp+arg_8], rbx
0x140028b45  push    rdi
0x140028b46  sub     rsp, 30h
0x140028b4a  mov     rax, [rcx+28h]
0x140028b4e  mov     rbx, r8
0x140028b51  mov     rdi, [rax+0B8h]
0x140028b58  mov     [rsp+38h+SessionId], 0
0x140028b60  mov     rcx, cs:WPP_GLOBAL_Control
0x140028b67  lea     rax, WPP_GLOBAL_Control
0x140028b6e  cmp     rcx, rax
0x140028b71  jz      short loc_140028B7D
0x140028b73  cmp     byte ptr [rcx+29h], 4
0x140028b77  jnb     loc_140028C35
0x140028b7d  xorps   xmm0, xmm0
0x140028b80  mov     r9d, 0FFFFFFFFh
0x140028b86  movups  xmmword ptr [rbx], xmm0
0x140028b89  mov     r11, [rdi+30h]
0x140028b8d  xor     ecx, ecx
0x140028b8f  mov     [rsp+38h+Value], r9d
0x140028b94  movups  xmmword ptr [rsp+38h+String.Length], xmm0
0x140028b99  movzx   r10d, word ptr [r11+58h]
0x140028b9e  mov     rax, [r11+60h]
0x140028ba2  mov     r8d, r10d
0x140028ba5  shr     r8d, 1
0x140028ba8  cmp     ecx, r8d
0x140028bab  jnb     short loc_140028C15
0x140028bad  cmp     word ptr [rax], 3Ah ; ':'
0x140028bb1  lea     rdx, [rax+2]
0x140028bb5  jz      short loc_140028BBE
0x140028bb7  mov     rax, rdx
0x140028bba  inc     ecx
0x140028bbc  jmp     short loc_140028BA8
0x140028bbe  movzx   eax, word ptr [r11+5Ah]
0x140028bc3  add     cx, cx
0x140028bc6  sub     ax, cx
0x140028bc9  mov     [rsp+38h+String.Buffer], rdx
0x140028bce  sub     ax, 2
0x140028bd2  sub     r10w, cx
0x140028bd6  mov     [rsp+38h+String.MaximumLength], ax
0x140028bdb  sub     r10w, 2
0x140028be0  movzx   eax, word ptr [rdx]
0x140028be3  sub     ax, 30h ; '0'
0x140028be7  mov     [rsp+38h+String.Length], r10w
0x140028bed  cmp     ax, 9
0x140028bf1  ja      short loc_140028C15
0x140028bf3  lea     r8, [rsp+38h+Value]; Value
0x140028bf8  xor     edx, edx; Base
0x140028bfa  lea     rcx, [rsp+38h+String]; String
0x140028bff  call    cs:__imp_RtlUnicodeStringToInteger
0x140028c06  nop     dword ptr [rax+rax+00h]
0x140028c0b  test    eax, eax
0x140028c0d  jz      short loc_140028C4F
0x140028c0f  mov     r9d, 0FFFFFFFFh
0x140028c15  mov     [rsp+38h+SessionId], r9d
0x140028c1a  cmp     r9d, 0FFFFFFFFh
0x140028c1e  jz      short loc_140028C56
0x140028c20  mov     eax, [rsp+38h+SessionId]
0x140028c24  mov     [rbx+8], eax
0x140028c27  xor     eax, eax
0x140028c29  mov     rbx, [rsp+38h+arg_8]
0x140028c2e  add     rsp, 30h
0x140028c32  pop     rdi
0x140028c33  retn
0x140028c35  mov     rcx, [rcx+18h]
0x140028c39  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140028c40  mov     edx, 41h ; 'A'
0x140028c45  call    WPP_SF_
0x140028c4a  jmp     loc_140028B7D
0x140028c4f  mov     r9d, [rsp+38h+Value]
0x140028c54  jmp     short loc_140028C15
0x140028c56  movzx   eax, byte ptr [rdi]
0x140028c59  cmp     al, 0Eh
0x140028c5b  jnz     short loc_140028C74
0x140028c5d  cmp     dword ptr [rdi+18h], 14018Fh
0x140028c64  jnz     short loc_140028C20
0x140028c66  mov     rax, [rdi+20h]
0x140028c6a  mov     rcx, [rax+8]
0x140028c6e  mov     rcx, [rcx+8]
0x140028c72  jmp     short loc_140028C85
0x140028c74  test    al, al
0x140028c76  jnz     short loc_140028C20
0x140028c78  mov     rax, [rdi+8]
0x140028c7c  test    rax, rax
0x140028c7f  jz      short loc_140028C20
0x140028c81  mov     rcx, [rax+8]
0x140028c85  add     rcx, 20h ; ' '
0x140028c89  jz      short loc_140028C20
0x140028c8b  mov     rax, [rcx]
0x140028c8e  lea     rdx, [rsp+38h+SessionId]; SessionId
0x140028c93  test    rax, rax
0x140028c96  jz      short loc_140028C9D
0x140028c98  mov     rcx, rax
0x140028c9b  jmp     short loc_140028CA1
0x140028c9d  mov     rcx, [rcx+10h]; Token
0x140028ca1  call    cs:__imp_SeQuerySessionIdToken
0x140028ca8  nop     dword ptr [rax+rax+00h]
0x140028cad  jmp     loc_140028C20
```
