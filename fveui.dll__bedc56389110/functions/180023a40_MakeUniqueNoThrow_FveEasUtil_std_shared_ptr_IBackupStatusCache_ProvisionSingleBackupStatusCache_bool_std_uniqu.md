# MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,ProvisionSingleBackupStatusCache,bool &>(std::unique_ptr<FveEasUtil,std::default_delete<FveEasUtil>> &,std::shared_ptr<IBackupStatusCache> &,ProvisionSingleBackupStatusCache &&,bool &)

- ea: `0x180023a40`
- end: `0x180023ad1`
- name: `??$MakeUniqueNoThrow@VFveEasUtil@@AEAV?$shared_ptr@VIBackupStatusCache@@@std@@W4ProvisionSingleBackupStatusCache@@AEA_N@@YAJAEAV?$unique_ptr@VFveEasUtil@@U?$default_delete@VFveEasUtil@@@std@@@std@@AEAV?$shared_ptr@VIBackupStatusCache@@@1@$$QEAW4ProvisionSingleBackupStatusCache@@AEA_N@Z`
- size: `145`
- prototype: `__int64 __fastcall(__int64 *, __int64, int *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027a3c`

## callees

- `0x180001c00`
- `0x180023a40`
- `0x180023eac`
- `0x180023efc`

## pseudocode

```c
__int64 __fastcall MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,enum ProvisionSingleBackupStatusCache,bool &>(
        __int64 *a1,
        __int64 a2,
        int *a3,
        char *a4)
{
  unsigned int v8; // edi
  _QWORD *v9; // rbx
  char v10; // al
  int v11; // edx
  char *v12; // rcx
  __int64 v13; // rdx

  try
  {
    v8 = 0;
    v9 = operator new(0x38u);
    v10 = *a4;
    v11 = *a3;
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
    v9[3] = 0;
    v12 = (char *)(v9 + 4);
    v9[4] = 0;
    v9[5] = 0;
    *((_BYTE *)v9 + 48) = v10;
    if ( v11 == 1 )
    {
      v12 = (char *)v9;
    }
    else if ( v11 )
    {
      if ( v11 != 2 )
        goto LABEL_8;
      v12 = (char *)(v9 + 2);
    }
    std::shared_ptr<IBackupStatusCache>::operator=(v12, a2);
LABEL_8:
    v13 = *a1;
    *a1 = (__int64)v9;
    if ( v13 )
      std::default_delete<FveEasUtil>::operator()();
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  v8 = 0;
}

```

## disassembly

```asm
0x180023a40  push    rbx
0x180023a42  push    rsi
0x180023a43  push    rdi
0x180023a44  push    r12
0x180023a46  push    r14
0x180023a48  push    r15
0x180023a4a  sub     rsp, 38h
0x180023a4e  mov     r15, r9
0x180023a51  mov     r12, r8
0x180023a54  mov     rsi, rdx
0x180023a57  mov     r14, rcx
0x180023a5a  xor     edi, edi
0x180023a5c  lea     ecx, [rdi+38h]; Size
0x180023a5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023a64  mov     rbx, rax
0x180023a67  mov     al, [r15]
0x180023a6a  mov     edx, [r12]
0x180023a6e  mov     [rbx], rdi
0x180023a71  mov     [rbx+8], rdi
0x180023a75  mov     [rbx+10h], rdi
0x180023a79  mov     [rbx+18h], rdi
0x180023a7d  lea     rcx, [rbx+20h]
0x180023a81  mov     [rcx], rdi
0x180023a84  mov     [rcx+8], rdi
0x180023a88  mov     [rbx+30h], al
0x180023a8b  cmp     edx, 1
0x180023a8e  jnz     short loc_180023A95
0x180023a90  mov     rcx, rbx
0x180023a93  jmp     short loc_180023AA2
0x180023a95  test    edx, edx
0x180023a97  jz      short loc_180023AA2
0x180023a99  cmp     edx, 2
0x180023a9c  jnz     short loc_180023AAA
0x180023a9e  lea     rcx, [rbx+10h]
0x180023aa2  mov     rdx, rsi
0x180023aa5  call    ??4?$shared_ptr@VIBackupStatusCache@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<IBackupStatusCache>::operator=(std::shared_ptr<IBackupStatusCache> const &)
0x180023aaa  mov     rdx, [r14]
0x180023aad  mov     [r14], rbx
0x180023ab0  test    rdx, rdx
0x180023ab3  jz      short loc_180023ABB
0x180023ab5  call    ??R?$default_delete@VFveEasUtil@@@std@@QEBAXPEAVFveEasUtil@@@Z; std::default_delete<FveEasUtil>::operator()(FveEasUtil *)
0x180023aba  nop
0x180023abb  jmp     short loc_180023AC1
0x180023abd  mov     edi, [rsp+68h+var_48]
0x180023ac1  mov     eax, edi
0x180023ac3  add     rsp, 38h
0x180023ac7  pop     r15
0x180023ac9  pop     r14
0x180023acb  pop     r12
0x180023acd  pop     rdi
0x180023ace  pop     rsi
0x180023acf  pop     rbx
0x180023ad0  retn
```
