# CacheClearingThread::Clear

- ea: `0x819f0`
- end: `0x81bcd`
- name: `CacheClearingThread::Clear`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x2f580`
- `0x2f5a0`
- `0x2f5b0`
- `0x2f5e0`
- `0x81880`
- `0x818a0`
- `0x818e0`
- `0x819d0`
- `0x819f0`

## string_xrefs

- `0x81a03`: `CacheClearingThread: CacheClearingThread started.`
- `0x81a10`: `CacheClearingThread: AutoEventCleanupThread going to sleep.`
- `0x81a33`: `CacheClearingThread: AutoEventCleanupThread woke up.`
- `0x81bb7`: `Exception occurred in CacheClearingThread. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x819f0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x819f5  ldarg.0
0x819f6  ldfld    valuetype [mscorlib]System.TimeSpan CacheClearingThread::_repeatTime
0x819fb  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x81a00  stloc.0
0x81a01  ldarg.0
0x81a02  ldc.i4.3
0x81a03  ldstr    aCacheclearingt// "CacheClearingThread: CacheClearingThrea"...
0x81a08  call     instance void CacheClearingThread::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x81a0d  nop
0x81a0e  ldarg.0
0x81a0f  ldc.i4.4
0x81a10  ldstr    aCacheclearingt_0// "CacheClearingThread: AutoEventCleanupTh"...
0x81a15  call     instance void CacheClearingThread::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x81a1a  ldarg.0
0x81a1b  call     instance class [mscorlib]System.Threading.AutoResetEvent CacheClearingThread::get_WakeUpEvent()
0x81a20  ldloc.0
0x81a21  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x81a26  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x81a2b  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan)
0x81a30  pop
0x81a31  ldarg.0
0x81a32  ldc.i4.4
0x81a33  ldstr    aCacheclearingt_1// "CacheClearingThread: AutoEventCleanupTh"...
0x81a38  call     instance void CacheClearingThread::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x81a3d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x81a42  ldc.r8   2.147483647e9
0x81a4b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x81a50  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x81a55  stloc.0
0x81a56  ldarg.0
0x81a57  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase> CacheClearingThread::_caches
0x81a5c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase>::GetEnumerator()
0x81a61  stloc.1
0x81a62  br       loc_81B69
0x81a67  ldloca.s 1
0x81a69  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase>::get_Current()
0x81a6e  stloc.2
0x81a6f  ldloc.2
0x81a70  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.LinkedListNode`1<class CacheItem>> Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::_propertyCache
0x81a75  stloc.3
0x81a76  ldc.i4.0
0x81a77  stloc.s  4
0x81a79  ldloc.3
0x81a7a  ldloca.s 4
0x81a7c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x81a81  ldloc.2
0x81a82  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::get_IsEmpty()
0x81a87  brtrue   loc_81B5C
0x81a8c  ldloc.2
0x81a8d  ldfld    class [System]System.Collections.Generic.LinkedList`1<class CacheItem> Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::_queue
0x81a92  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<class CacheItem>::get_Last()
0x81a97  stloc.s  5
0x81a99  ldloc.s  5
0x81a9b  callvirt instance var<u1> class [System]System.Collections.Generic.LinkedListNode`1<class CacheItem>::get_Value()
0x81aa0  callvirt instance valuetype [mscorlib]System.DateTime CacheItem::get_TimeStamp()
0x81aa5  ldloc.2
0x81aa6  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::get_RetentionTime()
0x81aab  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x81ab0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x81ab5  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x81aba  brfalse.s loc_81B21
0x81abc  br.s     loc_81AEF
0x81abe  ldloc.2
0x81abf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.LinkedListNode`1<class CacheItem>> Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::_propertyCache
0x81ac4  ldloc.s  5
0x81ac6  callvirt instance var<u1> class [System]System.Collections.Generic.LinkedListNode`1<class CacheItem>::get_Value()
0x81acb  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICacheable CacheItem::get_CacheElement()
0x81ad0  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ICacheable::get_Key()
0x81ad5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.LinkedListNode`1<class CacheItem>>::Remove(var<u1>)
0x81ada  pop
0x81adb  ldloc.s  5
0x81add  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedListNode`1<class CacheItem>::get_Next()
0x81ae2  stloc.s  5
0x81ae4  ldloc.2
0x81ae5  ldfld    class [System]System.Collections.Generic.LinkedList`1<class CacheItem> Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::_queue
0x81aea  callvirt instance void class [System]System.Collections.Generic.LinkedList`1<class CacheItem>::RemoveLast()
0x81aef  ldloc.s  5
0x81af1  brfalse.s loc_81B16
0x81af3  ldloc.s  5
0x81af5  callvirt instance var<u1> class [System]System.Collections.Generic.LinkedListNode`1<class CacheItem>::get_Value()
0x81afa  callvirt instance valuetype [mscorlib]System.DateTime CacheItem::get_TimeStamp()
0x81aff  ldloc.2
0x81b00  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::get_RetentionTime()
0x81b05  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x81b0a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x81b0f  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x81b14  brtrue.s loc_81ABE
0x81b16  ldloc.s  5
0x81b18  brtrue.s loc_81B21
0x81b1a  ldloc.2
0x81b1b  ldc.i4.1
0x81b1c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::set_IsEmpty(bool value)
0x81b21  ldloc.s  5
0x81b23  brfalse.s loc_81B5C
0x81b25  ldloc.0
0x81b26  ldloc.s  5
0x81b28  callvirt instance var<u1> class [System]System.Collections.Generic.LinkedListNode`1<class CacheItem>::get_Value()
0x81b2d  callvirt instance valuetype [mscorlib]System.DateTime CacheItem::get_TimeStamp()
0x81b32  ldloc.2
0x81b33  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::get_RetentionTime()
0x81b38  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x81b3d  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x81b42  brfalse.s loc_81B5C
0x81b44  ldloc.s  5
0x81b46  callvirt instance var<u1> class [System]System.Collections.Generic.LinkedListNode`1<class CacheItem>::get_Value()
0x81b4b  callvirt instance valuetype [mscorlib]System.DateTime CacheItem::get_TimeStamp()
0x81b50  ldloc.2
0x81b51  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase::get_RetentionTime()
0x81b56  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x81b5b  stloc.0
0x81b5c  leave.s  loc_81B69
0x81b5e  ldloc.s  4
0x81b60  brfalse.s loc_81B68
0x81b62  ldloc.3
0x81b63  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x81b68  endfinally
0x81b69  ldloca.s 1
0x81b6b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase>::MoveNext()
0x81b70  brtrue   loc_81A67
0x81b75  leave.s  loc_81B85
0x81b77  ldloca.s 1
0x81b79  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCacheBase>
0x81b7f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x81b84  endfinally
0x81b85  ldloc.0
0x81b86  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x81b8b  ldarg.0
0x81b8c  ldfld    valuetype [mscorlib]System.TimeSpan CacheClearingThread::_repeatTime
0x81b91  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x81b96  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x81b9b  brfalse.s loc_81BAE
0x81b9d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x81ba2  ldarg.0
0x81ba3  ldfld    valuetype [mscorlib]System.TimeSpan CacheClearingThread::_repeatTime
0x81ba8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x81bad  stloc.0
0x81bae  leave    loc_81A0D
0x81bb3  stloc.s  6
0x81bb5  ldarg.0
0x81bb6  ldc.i4.2
0x81bb7  ldstr    aExceptionOccur_25// "Exception occurred in CacheClearingThre"...
0x81bbc  ldloc.s  6
0x81bbe  call     string [mscorlib]System.String::Format(string, object)
0x81bc3  call     instance void CacheClearingThread::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x81bc8  leave    loc_81A0D
```
