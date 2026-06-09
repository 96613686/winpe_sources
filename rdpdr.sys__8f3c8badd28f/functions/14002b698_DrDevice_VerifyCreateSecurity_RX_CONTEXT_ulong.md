# DrDevice::VerifyCreateSecurity(_RX_CONTEXT *,ulong)

- ea: `0x14002b698`
- end: `0x14002b92a`
- name: `?VerifyCreateSecurity@DrDevice@@IEAAJPEAU_RX_CONTEXT@@K@Z`
- size: `658`
- prototype: `__int64 __fastcall(DrDevice *this, struct _RX_CONTEXT *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140011010`
- `0x14002b120`

## callees

- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x140026f90`
- `0x14002b698`

## import_xrefs

- `ntoskrnl!SeQuerySessionIdToken` at `0x14002b7b7`
- `ntoskrnl!SeQuerySessionIdToken` at `0x14002b7b7`
- `ntoskrnl!IoGetRequestorSessionId` at `0x14002b6ca`
- `ntoskrnl!IoGetRequestorSessionId` at `0x14002b6ca`

## pseudocode

```c
__int64 __fastcall DrDevice::VerifyCreateSecurity(DrDevice *this, struct _RX_CONTEXT *a2, int a3)
{
  NTSTATUS RequestorSessionId; // eax
  unsigned int v7; // edi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  PACCESS_STATE AccessState; // rax
  PACCESS_TOKEN ClientToken; // rcx
  NTSTATUS v13; // eax
  ULONG v15; // [rsp+58h] [rbp+10h] BYREF
  ULONG SessionId; // [rsp+68h] [rbp+20h] BYREF

  v15 = 0;
  SessionId = 0;
  RequestorSessionId = IoGetRequestorSessionId(a2->CurrentIrp, &v15);
  v7 = RequestorSessionId;
  if ( RequestorSessionId < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
        (unsigned int)RequestorSessionId);
    return v7;
  }
  else
  {
    if ( v15 == a3 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        return 0;
      v9 = 15;
LABEL_31:
      WPP_SF_(v8->AttachedDevice, v9, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
      return 0;
    }
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
          v15,
          *(_DWORD *)(*((_QWORD *)this + 4) + 1128LL));
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, v15 + 16, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
      if ( (unsigned __int8)DrIsSystemProcessRequest(a2->CurrentIrpSp->Parameters.WMI.ProviderId) )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          return 0;
        v9 = 21;
        goto LABEL_31;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
      SecurityContext = a2->CurrentIrpSp->Parameters.Create.SecurityContext;
      if ( SecurityContext )
      {
        AccessState = SecurityContext->AccessState;
        if ( AccessState )
        {
          ClientToken = AccessState->SubjectSecurityContext.ClientToken;
          if ( ClientToken )
          {
            v13 = SeQuerySessionIdToken(ClientToken, &SessionId);
            if ( v13 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  20,
                  WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                  (unsigned int)v13);
            }
            else
            {
              if ( SessionId == a3 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    18,
                    WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                    SessionId,
                    a3);
                return 0;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  19,
                  WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                  SessionId,
                  a3);
            }
          }
        }
      }
    }
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x14002b698  mov     rax, rsp
0x14002b69b  mov     [rax+8], rbx
0x14002b69f  mov     [rax+18h], rbp
0x14002b6a3  push    rsi
0x14002b6a4  push    rdi
0x14002b6a5  push    r14
0x14002b6a7  sub     rsp, 30h
0x14002b6ab  mov     rbp, rdx
0x14002b6ae  mov     dword ptr [rax+10h], 0
0x14002b6b5  mov     r14, rcx
0x14002b6b8  mov     dword ptr [rax+20h], 0
0x14002b6bf  lea     rdx, [rax+10h]; pSessionId
0x14002b6c3  mov     esi, r8d
0x14002b6c6  mov     rcx, [rbp+28h]; Irp
0x14002b6ca  call    cs:__imp_IoGetRequestorSessionId
0x14002b6d1  nop     dword ptr [rax+rax+00h]
0x14002b6d6  mov     edi, eax
0x14002b6d8  test    eax, eax
0x14002b6da  js      loc_14002B8E3
0x14002b6e0  mov     r9d, [rsp+48h+arg_8]
0x14002b6e5  cmp     r9d, esi
0x14002b6e8  jnz     short loc_14002B715
0x14002b6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b6f1  lea     rbx, WPP_GLOBAL_Control
0x14002b6f8  cmp     rcx, rbx
0x14002b6fb  jz      loc_14002B89C
0x14002b701  cmp     byte ptr [rcx+29h], 5
0x14002b705  jb      loc_14002B89C
0x14002b70b  mov     edx, 0Fh
0x14002b710  jmp     loc_14002B88C
0x14002b715  test    r9d, r9d
0x14002b718  jnz     loc_14002B8A0
0x14002b71e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b725  lea     rbx, WPP_GLOBAL_Control
0x14002b72c  cmp     rcx, rbx
0x14002b72f  jz      short loc_14002B74B
0x14002b731  cmp     byte ptr [rcx+29h], 4
0x14002b735  jb      short loc_14002B74B
0x14002b737  mov     rcx, [rcx+18h]
0x14002b73b  lea     edx, [r9+10h]
0x14002b73f  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b746  call    WPP_SF_
0x14002b74b  mov     rcx, [rbp+30h]
0x14002b74f  mov     rcx, [rcx+8]
0x14002b753  call    DrIsSystemProcessRequest
0x14002b758  test    al, al
0x14002b75a  jnz     loc_14002B875
0x14002b760  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b767  cmp     rcx, rbx
0x14002b76a  jz      short loc_14002B787
0x14002b76c  cmp     byte ptr [rcx+29h], 5
0x14002b770  jb      short loc_14002B787
0x14002b772  mov     rcx, [rcx+18h]
0x14002b776  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b77d  mov     edx, 11h
0x14002b782  call    WPP_SF_
0x14002b787  mov     rax, [rbp+30h]
0x14002b78b  mov     rax, [rax+8]
0x14002b78f  test    rax, rax
0x14002b792  jz      loc_14002B8DC
0x14002b798  mov     rax, [rax+8]
0x14002b79c  test    rax, rax
0x14002b79f  jz      loc_14002B8DC
0x14002b7a5  mov     rcx, [rax+20h]; Token
0x14002b7a9  test    rcx, rcx
0x14002b7ac  jz      loc_14002B8DC
0x14002b7b2  lea     rdx, [rsp+48h+SessionId]; SessionId
0x14002b7b7  call    cs:__imp_SeQuerySessionIdToken
0x14002b7be  nop     dword ptr [rax+rax+00h]
0x14002b7c3  test    eax, eax
0x14002b7c5  js      short loc_14002B841
0x14002b7c7  mov     r9d, [rsp+48h+SessionId]
0x14002b7cc  cmp     r9d, esi
0x14002b7cf  jnz     short loc_14002B809
0x14002b7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b7d8  cmp     rcx, rbx
0x14002b7db  jz      loc_14002B89C
0x14002b7e1  cmp     byte ptr [rcx+29h], 5
0x14002b7e5  jb      loc_14002B89C
0x14002b7eb  mov     rcx, [rcx+18h]
0x14002b7ef  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b7f6  mov     edx, 12h
0x14002b7fb  mov     [rsp+48h+var_28], esi
0x14002b7ff  call    WPP_SF_dd
0x14002b804  jmp     loc_14002B89C
0x14002b809  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b810  cmp     rcx, rbx
0x14002b813  jz      loc_14002B8DC
0x14002b819  cmp     byte ptr [rcx+29h], 5
0x14002b81d  jb      loc_14002B8DC
0x14002b823  mov     rcx, [rcx+18h]
0x14002b827  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b82e  mov     edx, 13h
0x14002b833  mov     [rsp+48h+var_28], esi
0x14002b837  call    WPP_SF_dd
0x14002b83c  jmp     loc_14002B8DC
0x14002b841  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b848  cmp     rcx, rbx
0x14002b84b  jz      loc_14002B8DC
0x14002b851  cmp     byte ptr [rcx+29h], 2
0x14002b855  jb      loc_14002B8DC
0x14002b85b  mov     rcx, [rcx+18h]
0x14002b85f  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b866  mov     edx, 14h
0x14002b86b  mov     r9d, eax
0x14002b86e  call    WPP_SF_d
0x14002b873  jmp     short loc_14002B8DC
0x14002b875  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b87c  cmp     rcx, rbx
0x14002b87f  jz      short loc_14002B89C
0x14002b881  cmp     byte ptr [rcx+29h], 4
0x14002b885  jb      short loc_14002B89C
0x14002b887  mov     edx, 15h
0x14002b88c  mov     rcx, [rcx+18h]
0x14002b890  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b897  call    WPP_SF_
0x14002b89c  xor     eax, eax
0x14002b89e  jmp     short loc_14002B916
0x14002b8a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b8a7  lea     rbx, WPP_GLOBAL_Control
0x14002b8ae  cmp     rcx, rbx
0x14002b8b1  jz      short loc_14002B8DC
0x14002b8b3  cmp     byte ptr [rcx+29h], 5
0x14002b8b7  jb      short loc_14002B8DC
0x14002b8b9  mov     rax, [r14+20h]
0x14002b8bd  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b8c4  mov     rcx, [rcx+18h]
0x14002b8c8  mov     edx, 16h
0x14002b8cd  mov     eax, [rax+468h]
0x14002b8d3  mov     [rsp+48h+var_28], eax
0x14002b8d7  call    WPP_SF_dd
0x14002b8dc  mov     eax, 0C0000022h
0x14002b8e1  jmp     short loc_14002B916
0x14002b8e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b8ea  lea     rbx, WPP_GLOBAL_Control
0x14002b8f1  cmp     rcx, rbx
0x14002b8f4  jz      short loc_14002B914
0x14002b8f6  cmp     byte ptr [rcx+29h], 2
0x14002b8fa  jb      short loc_14002B914
0x14002b8fc  mov     rcx, [rcx+18h]
0x14002b900  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b907  mov     edx, 17h
0x14002b90c  mov     r9d, edi
0x14002b90f  call    WPP_SF_d
0x14002b914  mov     eax, edi
0x14002b916  mov     rbx, [rsp+48h+arg_0]
0x14002b91b  mov     rbp, [rsp+48h+arg_10]
0x14002b920  add     rsp, 30h
0x14002b924  pop     r14
0x14002b926  pop     rdi
0x14002b927  pop     rsi
0x14002b928  retn
```
